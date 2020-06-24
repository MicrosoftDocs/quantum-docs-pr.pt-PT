---
title: Obter contagens de recursos
description: Saiba como obter estimativas de recursos usando um simulador de traços quânticos.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275886"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="7be9c-103">Obter contagens de recursos</span><span class="sxs-lookup"><span data-stu-id="7be9c-103">Obtaining resource counts</span></span>

<span data-ttu-id="7be9c-104">O custo de simulação de $n$ qubits em escalas de computadores clássicos exponencialmente com $n$.</span><span class="sxs-lookup"><span data-stu-id="7be9c-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="7be9c-105">Isto limita muito o tamanho de uma simulação de química quântica que podemos realizar com o simulador de estado inteiro.</span><span class="sxs-lookup"><span data-stu-id="7be9c-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="7be9c-106">Em grandes casos de química, podemos, no entanto, obter informações úteis.</span><span class="sxs-lookup"><span data-stu-id="7be9c-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="7be9c-107">Aqui, examinamos como os custos dos recursos, como o número de portões T-gates ou CNOT, para simular a química podem ser obtidos de forma automatizada usando o [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de traços.</span><span class="sxs-lookup"><span data-stu-id="7be9c-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="7be9c-108">Esta informação informa-nos de quando os computadores quânticos podem ser grandes o suficiente para executar estes algoritmos de química quântica.</span><span class="sxs-lookup"><span data-stu-id="7be9c-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="7be9c-109">Para referência, consulte a `GetGateCount` amostra fornecida.</span><span class="sxs-lookup"><span data-stu-id="7be9c-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="7be9c-110">Partamos do princípio de que já temos um `FermionHamiltonian` exemplo, por exemplo, carregado do esquema de Broombridge, tal como discutido no exemplo [de carregamento a partir de ficheiros.](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)</span><span class="sxs-lookup"><span data-stu-id="7be9c-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="7be9c-111">A sintaxe para obter estimativas de recursos é quase idêntica a executar o algoritmo no simulador de estado inteiro.</span><span class="sxs-lookup"><span data-stu-id="7be9c-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="7be9c-112">Simplesmente escolhemos uma máquina-alvo diferente.</span><span class="sxs-lookup"><span data-stu-id="7be9c-112">We simply choose a different target machine.</span></span> <span data-ttu-id="7be9c-113">Para efeitos de estimativas de recursos, basta avaliar o custo de um único passo Trotter, ou uma caminhada quântica criada pela técnica de Qubitização.</span><span class="sxs-lookup"><span data-stu-id="7be9c-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="7be9c-114">A placa de caldeira para invocar estes algoritmos é a seguinte.</span><span class="sxs-lookup"><span data-stu-id="7be9c-114">The boilerplate for invoking these algorithms is as follows.</span></span>

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

<span data-ttu-id="7be9c-115">Agora configuramos o simulador de rastreio para rastrear os recursos que nos interessam.</span><span class="sxs-lookup"><span data-stu-id="7be9c-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="7be9c-116">Neste caso, contamos operações quânticas primitivas, colocando a `usePrimitiveOperationsCounter` bandeira para `true` .</span><span class="sxs-lookup"><span data-stu-id="7be9c-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="7be9c-117">Um detalhe técnico `throwOnUnconstraintMeasurement` é definido para evitar `false` exceções nos casos em que o código Q# não afirma corretamente a probabilidade de resultados de medição, se forem realizados.</span><span class="sxs-lookup"><span data-stu-id="7be9c-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

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

<span data-ttu-id="7be9c-118">Agora corremos o algoritmo quântico do programa de motorista da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="7be9c-118">We now run the quantum algorithm from the driver program as follows.</span></span>

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