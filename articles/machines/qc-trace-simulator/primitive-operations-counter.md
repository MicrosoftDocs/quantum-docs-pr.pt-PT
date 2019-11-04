---
title: Contador de operações primitivas | Simulador de rastreamento de computador Quantum | Microsoft Docs
description: Visão geral do simulador de rastreamento de computador Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184887"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="ab41d-103">Contador de operações primitivas</span><span class="sxs-lookup"><span data-stu-id="ab41d-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="ab41d-104">O `Primitive Operations Counter` é uma parte do [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de computador Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab41d-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="ab41d-105">Ele conta o número de execuções primitivas usadas por cada operação invocada em um programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab41d-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="ab41d-106">Todas as operações de `Microsoft.Quantum.Primitive` são expressas em termos de rotações qubit únicas, T Gates, Single qubit Clifford Gates, CNOT Gates e medidas de qubit de vários Pauli observáveis.</span><span class="sxs-lookup"><span data-stu-id="ab41d-106">All operations from `Microsoft.Quantum.Primitive` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="ab41d-107">As estatísticas coletadas são agregadas nas bordas do grafo de chamada de operações.</span><span class="sxs-lookup"><span data-stu-id="ab41d-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="ab41d-108">Agora, vamos contar quantas `T` Gates são necessárias para implementar a operação `CCNOT`.</span><span class="sxs-lookup"><span data-stu-id="ab41d-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="ab41d-109">Usando o contador de operações primitivas C# dentro de um programa</span><span class="sxs-lookup"><span data-stu-id="ab41d-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="ab41d-110">Para verificar se `CCNOT` realmente requer 7 `T` Gates e que `CCNOTDriver` executa 8 `T` Gates, podemos usar o seguinte C# código:</span><span class="sxs-lookup"><span data-stu-id="ab41d-110">To check that `CCNOT` indeed requires 7 `T` gates and that `CCNOTDriver` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="ab41d-111">A primeira parte do programa executa `CCNOTDriver`.</span><span class="sxs-lookup"><span data-stu-id="ab41d-111">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="ab41d-112">Na segunda parte, usamos o método `QCTraceSimulator.GetMetric` para obter o número de T Gates executadas por `CCNOTDriver`:</span><span class="sxs-lookup"><span data-stu-id="ab41d-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `CCNOTDriver`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="ab41d-113">Quando `GetMetric` é chamado com dois parâmetros de tipo, ele retorna o valor da métrica associada a uma determinada borda de gráfico de chamada.</span><span class="sxs-lookup"><span data-stu-id="ab41d-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="ab41d-114">Em nosso `Primitive.CCNOT` de operação de exemplo é chamado dentro de `CCNOTDriver` e, portanto, o grafo de chamadas contém o `<Primitive.CCNOT,CCNOTDriver>`de borda.</span><span class="sxs-lookup"><span data-stu-id="ab41d-114">In our example operation `Primitive.CCNOT` is called within `CCNOTDriver` and therefore the call graph contains the edge `<Primitive.CCNOT,CCNOTDriver>`.</span></span> 

<span data-ttu-id="ab41d-115">Para obter o número de `CNOT` Gates usado, podemos adicionar a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="ab41d-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="ab41d-116">Por fim, para gerar todas as estatísticas coletadas pelo contador portão no formato CSV, podemos usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ab41d-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="ab41d-117">Ver também</span><span class="sxs-lookup"><span data-stu-id="ab41d-117">See also</span></span> ##

- <span data-ttu-id="ab41d-118">A visão geral do [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab41d-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
