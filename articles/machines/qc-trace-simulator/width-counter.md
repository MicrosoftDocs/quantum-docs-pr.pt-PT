---
title: Balcão de Largura  Simulador de vestígios de computador quântico  Microsoft Docs
description: Descrição geral do simulador de rastreio do computador quântico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820373"
---
# <a name="width-counter"></a><span data-ttu-id="a465d-103">Contador de largura</span><span class="sxs-lookup"><span data-stu-id="a465d-103">Width Counter</span></span>

<span data-ttu-id="a465d-104">O `Width Counter` conta o número de qubits atribuídos e emprestados por cada operação.</span><span class="sxs-lookup"><span data-stu-id="a465d-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="a465d-105">Todas as operações do espaço de nome `Microsoft.Quantum.Intrinsic` são expressas em termos de rotações simples de qubit, portões T, portões simples de Qubit Clifford, portões CNOT e medições de observáveis multiqubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="a465d-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="a465d-106">Algumas das operações primitivas podem alocar qubits extras.</span><span class="sxs-lookup"><span data-stu-id="a465d-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="a465d-107">Por exemplo, multiplique portões `X` controlados ou portões de `T` controlados.</span><span class="sxs-lookup"><span data-stu-id="a465d-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="a465d-108">Calculemos o número de qubits extra atribuídos pela implementação de um portão de `X` controlado multiplicado:</span><span class="sxs-lookup"><span data-stu-id="a465d-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="a465d-109">Utilização do C# Contador de Largura dentro de um Programa</span><span class="sxs-lookup"><span data-stu-id="a465d-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="a465d-110">Multiplicar `X` controlados num total de 5 qubits atribuirá 2 qubits auxiliares e a sua largura de entrada será de 5.</span><span class="sxs-lookup"><span data-stu-id="a465d-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="a465d-111">Para verificar se este é o caso, podemos usar o seguinte C# programa:</span><span class="sxs-lookup"><span data-stu-id="a465d-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="a465d-112">A primeira parte do programa executa `ApplyMultiControlledX`.</span><span class="sxs-lookup"><span data-stu-id="a465d-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="a465d-113">Na segunda parte utilizamos o método `QCTraceSimulator.GetMetric` para obter o número de qubits atribuídos, bem como o número de qubits que controlou `X` recebidos como entrada.</span><span class="sxs-lookup"><span data-stu-id="a465d-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="a465d-114">Finalmente, para obter todas as estatísticas recolhidas por contador de largura em formato CSV podemos usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a465d-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="a465d-115">Ver também</span><span class="sxs-lookup"><span data-stu-id="a465d-115">See also</span></span> ##

- <span data-ttu-id="a465d-116">A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="a465d-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
