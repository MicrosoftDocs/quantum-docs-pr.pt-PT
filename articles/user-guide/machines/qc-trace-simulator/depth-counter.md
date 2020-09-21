---
title: Contador de profundidade - Kit de Desenvolvimento Quântico
description: Conheça o contador de profundidade microsoft QDK, que utiliza o simulador de traços Quânticos para recolher contagens da profundidade de cada operação invocada num Q# programa.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8280783adfcc2867c3a598a6f57d827125aadcfd
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833452"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="67d15-103">Simulador de vestígios quânticos: contador de profundidade</span><span class="sxs-lookup"><span data-stu-id="67d15-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="67d15-104">O contador de profundidade faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="67d15-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="67d15-105">Pode usá-lo para recolher contagens que representam o limite inferior da profundidade de cada operação invocada num programa quântico.</span><span class="sxs-lookup"><span data-stu-id="67d15-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="67d15-106">Valores de profundidade</span><span class="sxs-lookup"><span data-stu-id="67d15-106">Depth values</span></span>

<span data-ttu-id="67d15-107">Por predefinição, todas as operações têm uma profundidade de **0,** exceto a `T` operação, que tem uma profundidade de **1**.</span><span class="sxs-lookup"><span data-stu-id="67d15-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="67d15-108">Isto significa que, por defeito, apenas a `T` profundidade das operações é calculada (o que é muitas vezes desejável).</span><span class="sxs-lookup"><span data-stu-id="67d15-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="67d15-109">O contador de profundidade agrega e recolhe estatísticas sobre todas as bordas do gráfico de chamada da [operação](https://en.wikipedia.org/wiki/Call_graph).</span><span class="sxs-lookup"><span data-stu-id="67d15-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="67d15-110">Todas as <xref:microsoft.quantum.intrinsic> operações são expressas em termos de rotações de um único qubit, <xref:microsoft.quantum.intrinsic.t> operações, operações <xref:microsoft.quantum.intrinsic.cnot> e medições de observações pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="67d15-110">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, <xref:microsoft.quantum.intrinsic.t> operations, single-qubit Clifford operations, <xref:microsoft.quantum.intrinsic.cnot> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="67d15-111">Os utilizadores podem definir a profundidade para cada uma das operações primitivas através do `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="67d15-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="67d15-112">Invocando o contador de profundidade</span><span class="sxs-lookup"><span data-stu-id="67d15-112">Invoking the depth counter</span></span>

<span data-ttu-id="67d15-113">Para executar o simulador de traços quânticos com o contador de profundidade, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a sua `UseDepthCounter` propriedade para **verdade**, e, em seguida, criar um novo exemplo com como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="67d15-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="67d15-114">Usando o contador de profundidade num programa de anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="67d15-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="67d15-115">O exemplo C# que segue nesta secção calcula a `T` profundidade da `CCNOT` operação, com base no seguinte Q# código de amostra:</span><span class="sxs-lookup"><span data-stu-id="67d15-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="67d15-116">Para verificar se `CCNOT` tem `T` profundidade **5** e `ApplySampleWithCCNOT` tem profundidade `T` **6,** utilize o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="67d15-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="67d15-117">A primeira parte do programa `ApplySampleWithCCNOT` é.</span><span class="sxs-lookup"><span data-stu-id="67d15-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="67d15-118">A segunda parte utiliza o [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar a profundidade de e `T` `CCNOT` `ApplySampleWithCCNOT` .</span><span class="sxs-lookup"><span data-stu-id="67d15-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="67d15-119">Finalmente, pode descodutar todas as estatísticas recolhidas pelo contador de profundidade no formato CSV utilizando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="67d15-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="67d15-120">Ver também</span><span class="sxs-lookup"><span data-stu-id="67d15-120">See also</span></span>

- <span data-ttu-id="67d15-121">A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="67d15-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="67d15-122">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.</span><span class="sxs-lookup"><span data-stu-id="67d15-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="67d15-123">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.</span><span class="sxs-lookup"><span data-stu-id="67d15-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="67d15-124">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> referência da API.</span><span class="sxs-lookup"><span data-stu-id="67d15-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
