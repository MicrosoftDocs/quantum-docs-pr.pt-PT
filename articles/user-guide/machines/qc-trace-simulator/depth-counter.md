---
title: Contador de profundidade
description: Conheça o Contador de Profundidade QDK da Microsoft, que reúne contagens da profundidade de cada operação invocada num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275627"
---
# <a name="depth-counter"></a><span data-ttu-id="63a7a-103">Contador de profundidade</span><span class="sxs-lookup"><span data-stu-id="63a7a-103">Depth Counter</span></span>

<span data-ttu-id="63a7a-104">Faz `Depth Counter` parte do [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de rastreio de computador quântico.</span><span class="sxs-lookup"><span data-stu-id="63a7a-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="63a7a-105">É usado para recolher contagens da profundidade de cada operação invocada num programa quântico.</span><span class="sxs-lookup"><span data-stu-id="63a7a-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="63a7a-106">Todas as operações <xref:microsoft.quantum.intrinsic> são expressas em termos de rotações de qubit único, portões T, portões de Clifford de qubit único, portões CNOT e medições de observáveis Pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="63a7a-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="63a7a-107">Os utilizadores podem definir a profundidade para cada uma das operações primitivas através do `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="63a7a-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="63a7a-108">Por predefinição, todas as operações têm profundidade 0, exceto o portão T que tem profundidade 1.</span><span class="sxs-lookup"><span data-stu-id="63a7a-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="63a7a-109">Isto significa que, por defeito, apenas a profundidade T das operações é calculada (o que é muitas vezes desejável).</span><span class="sxs-lookup"><span data-stu-id="63a7a-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="63a7a-110">As estatísticas recolhidas são agregadas em todas as bordas do gráfico de chamadas de operações.</span><span class="sxs-lookup"><span data-stu-id="63a7a-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="63a7a-111">Vamos agora calcular a <xref:microsoft.quantum.intrinsic.t> profundidade da <xref:microsoft.quantum.intrinsic.ccnot> operação.</span><span class="sxs-lookup"><span data-stu-id="63a7a-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="63a7a-112">Utilizaremos o seguinte código de amostra Q#:</span><span class="sxs-lookup"><span data-stu-id="63a7a-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="63a7a-113">Utilização do Contador de Profundidade dentro de um programa C#</span><span class="sxs-lookup"><span data-stu-id="63a7a-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="63a7a-114">Para verificar se `CCNOT` tem `T` profundidade 5 e tem profundidade `ApplySampleWithCCNOT` `T` 6, podemos usar o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="63a7a-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="63a7a-115">A primeira parte do programa `ApplySampleWithCCNOT` executa.</span><span class="sxs-lookup"><span data-stu-id="63a7a-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="63a7a-116">Na segunda parte, usamos o método `QCTraceSimulator.GetMetric` para obter a profundidade de `T` `CCNOT` `ApplySampleWithCCNOT` e:</span><span class="sxs-lookup"><span data-stu-id="63a7a-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="63a7a-117">Finalmente, para obter todas as estatísticas `Depth Counter` recolhidas em formato CSV podemos utilizar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="63a7a-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="63a7a-118">Ver também</span><span class="sxs-lookup"><span data-stu-id="63a7a-118">See also</span></span> ##

- <span data-ttu-id="63a7a-119">A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.</span><span class="sxs-lookup"><span data-stu-id="63a7a-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
