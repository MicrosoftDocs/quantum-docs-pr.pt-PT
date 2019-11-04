---
title: Obtendo contagens de recursos | Microsoft Docs
description: Obtendo documentos de contagem de recursos
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: b28a27c4c1f1e64644fcfb074a731ff7b65cacb6
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184088"
---
## <a name="obtaining-resource-counts"></a>Obtendo contagens de recursos

O custo de simular $n $ qubits em um computador clássico é dimensionado exponencialmente com $n $. Isso limita bastante o tamanho de uma simulação de química do Quantum que pode ser executada com o simulador de estado completo. Para grandes instâncias de química, poderemos, no entanto, obter informações úteis. Aqui, examinamos como os custos de recursos, como o número de T-Gates ou CNOT Gates, para simular a química podem ser obtidos de maneira automatizada usando o [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro). Essas informações informam quando os computadores Quantum podem ser grandes o suficiente para executar esses algoritmos de química da Quantum. Para referência, consulte o exemplo de `GetGateCount` fornecido.

Vamos supor que já temos uma instância de `FermionHamiltonian`, digamos, carregada do esquema Broombridge, conforme discutido no exemplo de [carregamento de arquivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) . 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

A sintaxe para obter estimativas de recursos é quase idêntica à execução do algoritmo no simulador de estado completo. Simplesmente escolhemos um computador de destino diferente. Para fins de estimativas de recursos, é suficiente avaliar o custo de uma única etapa Trotter ou uma movimentação Quantum criada pela técnica Qubitization. O texto clichê para invocar esses algoritmos é o seguinte.

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

Agora, configuramos o simulador de rastreamento para acompanhar os recursos nos quais estamos interessados. Nesse caso, contamos operações Quantum primitivas definindo o sinalizador `usePrimitiveOperationsCounter` como `true`. Um `throwOnUnconstraintMeasurement` de detalhes técnicos é definido como `false` para evitar exceções em casos em que o código Q # não é corretamente declarado de probabiltiy de resultados de medida, se algum for executado.

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

Agora, executamos o algoritmo Quantum do programa de driver da seguinte maneira.

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