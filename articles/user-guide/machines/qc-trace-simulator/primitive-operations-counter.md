---
title: Contador de operação primitiva - Kit de Desenvolvimento Quântico
description: 'Saiba mais sobre o contador de operações primitivos microsoft QDK, que usa o simulador de traços quânticos para rastrear processos primitivos usados por operações num Q# programa.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690961"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="875b7-103">Simulador de vestígios quânticos: contador de operações primitivas</span><span class="sxs-lookup"><span data-stu-id="875b7-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="875b7-104">O contador de operações primitiva faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="875b7-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="875b7-105">Conta o número de processos primitivos usados por cada operação invocada num programa quântico.</span><span class="sxs-lookup"><span data-stu-id="875b7-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="875b7-106">Todas as <xref:Microsoft.Quantum.Intrinsic> operações são expressas em termos de rotações de um único qubit, operações T, operações de Clifford de um único qubit, operações CNOT e medições de observáveis Pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="875b7-106">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="875b7-107">O Contador de Operações Primitiva agrega e recolhe estatísticas sobre todas as bordas do gráfico de chamada da [operação](https://en.wikipedia.org/wiki/Call_graph).</span><span class="sxs-lookup"><span data-stu-id="875b7-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="875b7-108">Invocando o contador de operações primitiva</span><span class="sxs-lookup"><span data-stu-id="875b7-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="875b7-109">Para executar o simulador de traços quânticos com o contador de operação primitivo, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UsePrimitiveOperationsCounter` propriedade para **verdade** , e, em seguida, criar um novo caso com o como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="875b7-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="875b7-110">Usando o contador de operações primitiva num programa de anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="875b7-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="875b7-111">O exemplo C# que se segue nesta secção conta quantas <xref:Microsoft.Quantum.Intrinsic.T> operações são necessárias para implementar a <xref:Microsoft.Quantum.Intrinsic.ccnot> operação, com base no seguinte Q# código de amostra:</span><span class="sxs-lookup"><span data-stu-id="875b7-111">The C# example that follows in this section counts how many <xref:Microsoft.Quantum.Intrinsic.T> operations are needed to implement the <xref:Microsoft.Quantum.Intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="875b7-112">Para verificar se `CCNOT` são necessárias sete `T` operações e que `ApplySampleWithCCNOT` executa oito `T` operações, utilize o seguinte código C# :</span><span class="sxs-lookup"><span data-stu-id="875b7-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="875b7-113">A primeira parte do programa `ApplySampleWithCCNOT` é.</span><span class="sxs-lookup"><span data-stu-id="875b7-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="875b7-114">A segunda parte utiliza o [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar o número de `T` operações executadas `ApplySampleWithCCNOT` por:</span><span class="sxs-lookup"><span data-stu-id="875b7-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="875b7-115">Quando se liga `GetMetric` com dois parâmetros do tipo, devolve o valor da métrica associada a uma determinada borda do gráfico de chamada.</span><span class="sxs-lookup"><span data-stu-id="875b7-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="875b7-116">No exemplo anterior, o programa chama a `Primitive.CCNOT` operação interior `ApplySampleWithCCNOT` e, portanto, o gráfico de chamada contém a borda `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="875b7-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="875b7-117">Para recuperar o número de `CNOT` operações utilizadas, adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="875b7-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="875b7-118">Finalmente, pode descodutar todas as estatísticas recolhidas pelo Contador de Operações Primitivas em formato CSV utilizando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="875b7-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="875b7-119">Ver também</span><span class="sxs-lookup"><span data-stu-id="875b7-119">See also</span></span>

- <span data-ttu-id="875b7-120">A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="875b7-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="875b7-121">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.</span><span class="sxs-lookup"><span data-stu-id="875b7-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="875b7-122">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.</span><span class="sxs-lookup"><span data-stu-id="875b7-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="875b7-123">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> referência da API.</span><span class="sxs-lookup"><span data-stu-id="875b7-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>