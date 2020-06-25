---
title: Contador de Operações Primitivas
description: Conheça o Contador de Operações Primitivas da Microsoft QDK, que acompanha o número de execuções primitivas usadas por operações num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275556"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="f26a7-103">Contador de Operações Primitivas</span><span class="sxs-lookup"><span data-stu-id="f26a7-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="f26a7-104">Faz `Primitive Operations Counter` parte do [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de rastreio de computador quântico.</span><span class="sxs-lookup"><span data-stu-id="f26a7-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="f26a7-105">Conta o número de execuções primitivas usadas por todas as operações invocadas num programa quântico.</span><span class="sxs-lookup"><span data-stu-id="f26a7-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="f26a7-106">Todas as operações `Microsoft.Quantum.Intrinsic` são expressas em termos de rotações de qubit único, portões T, portões de Clifford de qubit único, portões CNOT e medições de observáveis Pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="f26a7-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="f26a7-107">As estatísticas recolhidas são agregadas sobre as bordas do gráfico de chamadas de operações.</span><span class="sxs-lookup"><span data-stu-id="f26a7-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="f26a7-108">Contemos agora quantos `T` portões são necessários para implementar a `CCNOT` operação.</span><span class="sxs-lookup"><span data-stu-id="f26a7-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="f26a7-109">Utilização do Contador de Operações Primitivas dentro de um Programa C#</span><span class="sxs-lookup"><span data-stu-id="f26a7-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="f26a7-110">Para verificar `CCNOT` se, de facto, requer 7 `T` portões e que `ApplySampleWithCCNOT` executa 8 `T` portões podemos usar o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="f26a7-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="f26a7-111">A primeira parte do programa `ApplySampleWithCCNOT` executa.</span><span class="sxs-lookup"><span data-stu-id="f26a7-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="f26a7-112">Na segunda parte, usamos o método `QCTraceSimulator.GetMetric` para executar o número de portões T `ApplySampleWithCCNOT` por:</span><span class="sxs-lookup"><span data-stu-id="f26a7-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="f26a7-113">Quando `GetMetric` é chamado com dois parâmetros de tipo, devolve o valor da métrica associada a uma determinada borda do gráfico de chamada.</span><span class="sxs-lookup"><span data-stu-id="f26a7-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="f26a7-114">No nosso exemplo, a `Primitive.CCNOT` operação é chamada dentro `ApplySampleWithCCNOT` e, portanto, o gráfico de chamada contém a borda `<Primitive.CCNOT, ApplySampleWithCCNOT>` .</span><span class="sxs-lookup"><span data-stu-id="f26a7-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="f26a7-115">Para obter o número de `CNOT` portões usados, podemos adicionar a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="f26a7-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="f26a7-116">Finalmente, para obter todas as estatísticas recolhidas pelo contador de portais em formato CSV podemos utilizar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f26a7-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="f26a7-117">Ver também</span><span class="sxs-lookup"><span data-stu-id="f26a7-117">See also</span></span> ##

- <span data-ttu-id="f26a7-118">A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.</span><span class="sxs-lookup"><span data-stu-id="f26a7-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
