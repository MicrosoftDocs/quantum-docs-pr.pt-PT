---
title: Obter contagens de recursos
description: Saiba como obter estimativas de recursos usando um simulador de traços quânticos.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: b8974114a5629fa1928b5774e79aba93fa3d1f7d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856232"
---
# <a name="obtaining-resource-counts"></a>Obter contagens de recursos

O custo de simulação de $n$ qubits em escalas de computadores clássicos exponencialmente com $n$. Isto limita muito o tamanho de uma simulação de química quântica que podemos realizar com o simulador de estado inteiro. Em grandes casos de química, podemos, no entanto, obter informações úteis. Aqui, examinamos como os custos dos recursos, como o número de portões T-gates ou CNOT, para simular a química podem ser obtidos de forma automatizada usando o [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de traços. Esta informação informa-nos de quando os computadores quânticos podem ser grandes o suficiente para executar estes algoritmos de química quântica. Para referência, consulte a `GetGateCount` amostra fornecida.

Partamos do princípio de que já temos um `FermionHamiltonian` exemplo, por exemplo, carregado do esquema de Broombridge, tal como discutido no exemplo [de carregamento a partir de ficheiros.](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

A sintaxe para obter estimativas de recursos é quase idêntica a executar o algoritmo no simulador de estado inteiro. Simplesmente escolhemos uma máquina-alvo diferente. Para efeitos de estimativas de recursos, basta avaliar o custo de um único passo Trotter, ou uma caminhada quântica criada pela técnica de Qubitização. A placa de caldeira para invocar estes algoritmos é a seguinte.

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

Agora configuramos o simulador de rastreio para rastrear os recursos que nos interessam. Neste caso, contamos operações quânticas primitivas, colocando a `usePrimitiveOperationsCounter` bandeira para `true` . Um detalhe técnico `throwOnUnconstraintMeasurement` é definido para evitar `false` exceções nos casos em que o Q# código não afirma corretamente a probabilidade de resultados de medição, se algum for realizado.

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

Agora corremos o algoritmo quântico do programa de motorista da seguinte forma.

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```