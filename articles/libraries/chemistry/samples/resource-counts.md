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
## <a name="obtaining-resource-counts"></a><span data-ttu-id="c1a60-103">Obtendo contagens de recursos</span><span class="sxs-lookup"><span data-stu-id="c1a60-103">Obtaining resource counts</span></span>

<span data-ttu-id="c1a60-104">O custo de simular $n $ qubits em um computador clássico é dimensionado exponencialmente com $n $.</span><span class="sxs-lookup"><span data-stu-id="c1a60-104">The cost of simulating $n$ qubits on a classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="c1a60-105">Isso limita bastante o tamanho de uma simulação de química do Quantum que pode ser executada com o simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="c1a60-105">This greatly limits the size of an quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="c1a60-106">Para grandes instâncias de química, poderemos, no entanto, obter informações úteis.</span><span class="sxs-lookup"><span data-stu-id="c1a60-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="c1a60-107">Aqui, examinamos como os custos de recursos, como o número de T-Gates ou CNOT Gates, para simular a química podem ser obtidos de maneira automatizada usando o [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="c1a60-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="c1a60-108">Essas informações informam quando os computadores Quantum podem ser grandes o suficiente para executar esses algoritmos de química da Quantum.</span><span class="sxs-lookup"><span data-stu-id="c1a60-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="c1a60-109">Para referência, consulte o exemplo de `GetGateCount` fornecido.</span><span class="sxs-lookup"><span data-stu-id="c1a60-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="c1a60-110">Vamos supor que já temos uma instância de `FermionHamiltonian`, digamos, carregada do esquema Broombridge, conforme discutido no exemplo de [carregamento de arquivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="c1a60-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="c1a60-111">A sintaxe para obter estimativas de recursos é quase idêntica à execução do algoritmo no simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="c1a60-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="c1a60-112">Simplesmente escolhemos um computador de destino diferente.</span><span class="sxs-lookup"><span data-stu-id="c1a60-112">We simply choose a different target machine.</span></span> <span data-ttu-id="c1a60-113">Para fins de estimativas de recursos, é suficiente avaliar o custo de uma única etapa Trotter ou uma movimentação Quantum criada pela técnica Qubitization.</span><span class="sxs-lookup"><span data-stu-id="c1a60-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="c1a60-114">O texto clichê para invocar esses algoritmos é o seguinte.</span><span class="sxs-lookup"><span data-stu-id="c1a60-114">The boilerplate for invoking these algorithms are as follows.</span></span>

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

<span data-ttu-id="c1a60-115">Agora, configuramos o simulador de rastreamento para acompanhar os recursos nos quais estamos interessados.</span><span class="sxs-lookup"><span data-stu-id="c1a60-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="c1a60-116">Nesse caso, contamos operações Quantum primitivas definindo o sinalizador `usePrimitiveOperationsCounter` como `true`.</span><span class="sxs-lookup"><span data-stu-id="c1a60-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="c1a60-117">Um `throwOnUnconstraintMeasurement` de detalhes técnicos é definido como `false` para evitar exceções em casos em que o código Q # não é corretamente declarado de probabiltiy de resultados de medida, se algum for executado.</span><span class="sxs-lookup"><span data-stu-id="c1a60-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probabiltiy of measurement outcomes, if any are performed.</span></span>

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

<span data-ttu-id="c1a60-118">Agora, executamos o algoritmo Quantum do programa de driver da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="c1a60-118">We now run the quantum algorithm from the driver program as follows.</span></span>

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