---
title: Contador de Operações Primitivas  Simulador de vestígios de computador quântico  Microsoft Docs
description: Descrição geral do simulador de rastreio do computador quântico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820424"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="04438-103">Contador de Operações Primitivas</span><span class="sxs-lookup"><span data-stu-id="04438-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="04438-104">O `Primitive Operations Counter` faz parte do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="04438-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="04438-105">Conta o número de execuções primitivas usadas por cada operação invocada num programa quântico.</span><span class="sxs-lookup"><span data-stu-id="04438-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="04438-106">Todas as operações de `Microsoft.Quantum.Intrinsic` são expressas em termos de rotações de qubit simples, portões T, portões simples de Qubit Clifford, portões CNOT e medições de observáveis multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="04438-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="04438-107">As estatísticas recolhidas são agregadas sobre as bordas do gráfico de chamadas de operações.</span><span class="sxs-lookup"><span data-stu-id="04438-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="04438-108">Contemos agora quantas portas `T` são necessárias para implementar a operação `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="04438-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="04438-109">Utilização do Contador C# de Operações Primitivas dentro de um Programa</span><span class="sxs-lookup"><span data-stu-id="04438-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="04438-110">Para verificar se `CCNOT` requer 7 portões `T` e que `ApplySampleWithCCNOT` executa C# 8 portas `T` podemos usar o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="04438-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="04438-111">A primeira parte do programa executa `ApplySampleWithCCNOT`.</span><span class="sxs-lookup"><span data-stu-id="04438-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="04438-112">Na segunda parte, utilizamos o método `QCTraceSimulator.GetMetric` para executar o número de portões T por `ApplySampleWithCCNOT`:</span><span class="sxs-lookup"><span data-stu-id="04438-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="04438-113">Quando `GetMetric` é chamado com dois parâmetros de tipo, devolve o valor da métrica associada a uma determinada borda do gráfico de chamada.</span><span class="sxs-lookup"><span data-stu-id="04438-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="04438-114">No nosso exemplo, a operação `Primitive.CCNOT` é chamada dentro `ApplySampleWithCCNOT` e, portanto, o gráfico de chamada contém a borda `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span><span class="sxs-lookup"><span data-stu-id="04438-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="04438-115">Para obter o número de portões `CNOT` usados, podemos adicionar a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="04438-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="04438-116">Finalmente, para obter todas as estatísticas recolhidas pelo balcão do portal em formato CSV podemos usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04438-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="04438-117">Ver também</span><span class="sxs-lookup"><span data-stu-id="04438-117">See also</span></span> ##

- <span data-ttu-id="04438-118">A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="04438-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
