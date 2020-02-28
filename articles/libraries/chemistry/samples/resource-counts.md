---
title: Obter contagens de recursos
description: Aprenda a obter estimativas de recursos usando um simulador de vestígios quânticos.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907839"
---
# <a name="obtaining-resource-counts"></a>Obter contagens de recursos

O custo de simulação de $n qubits de $n dólares em escalas de computadores clássicos exponencialmente com $n$. Isto limita muito o tamanho de uma simulação de química quântica que podemos realizar com o simulador de estado inteiro. Para grandes instâncias de química, podemos, no entanto, obter informações úteis. Aqui, examinamos como os custos de recursos, como o número de portões T ou CNOT, para simular química podem ser obtidos de forma automatizada usando o simulador de [vestígios](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Tal informação informa-nos de quando os computadores quânticos podem ser grandes o suficiente para executar estes algoritmos de química quântica. Para referência, consulte a amostra `GetGateCount` fornecida.

Partamos do princípio de que já temos um `FermionHamiltonian` caso, por exemplo, carregado do esquema de Broombridge, tal como discutido no exemplo do [loading-from-file.](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

A sintaxe para obter estimativas de recursos é quase idêntica à execução do algoritmo no simulador de estado inteiro. Simplesmente escolhemos uma máquina alvo diferente. Para efeitos de estimativas de recursos, basta avaliar o custo de um único passo trotter, ou uma caminhada quântica criada pela técnica de Qubitização. A placa de caldeira para invocar estes algoritmos é a seguinte.

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

Agora configuramos o simulador de vestígios para rastrear os recursos que nos interessam. Neste caso, contamos operações quânticas primitivas colocando a bandeira `usePrimitiveOperationsCounter` para `true`. Um detalhe técnico `throwOnUnconstraintMeasurement` está definido para `false` evitar exceções nos casos em que o código Q# não afirme corretamente a probabilidade de resultados de medição, se algum for realizado.

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

Agora executamos o algoritmo quântico do programa de motoristada da seguinte forma.

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