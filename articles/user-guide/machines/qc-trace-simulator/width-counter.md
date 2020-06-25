---
title: Contador de largura
description: Saiba mais sobre o Contador de Largura QDK do Microsoft, que conta o número de qubits atribuídos e emprestados por cada operação num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275563"
---
# <a name="width-counter"></a><span data-ttu-id="6d0d3-103">Contador de largura</span><span class="sxs-lookup"><span data-stu-id="6d0d3-103">Width Counter</span></span>

<span data-ttu-id="6d0d3-104">O `Width Counter` número de qubits atribuídos e emprestados por cada operação.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="6d0d3-105">Todas as operações do `Microsoft.Quantum.Intrinsic` espaço de nome são expressas em termos de rotações de qubit único, portões T, portões de Clifford de qubit único, portões CNOT e medições de observáveis Pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="6d0d3-106">Algumas das operações primitivas podem alocar qubits extra.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="6d0d3-107">Por exemplo, multiplique `X` portões controlados ou `T` portões controlados.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="6d0d3-108">Vamos calcular o número de qubits extra atribuídos pela implementação de um portão controlado por `X` multiplicação:</span><span class="sxs-lookup"><span data-stu-id="6d0d3-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="6d0d3-109">Utilização do Contador de Largura dentro de um programa C#</span><span class="sxs-lookup"><span data-stu-id="6d0d3-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="6d0d3-110">A atuação controlada por `X` multiplicação num total de 5 qubits irá afetar 2 qubits auxiliares e a sua largura de entrada será de 5.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="6d0d3-111">Para verificar se este é o caso, podemos usar o seguinte programa C#:</span><span class="sxs-lookup"><span data-stu-id="6d0d3-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="6d0d3-112">A primeira parte do programa `ApplyMultiControlledX` executa.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="6d0d3-113">Na segunda parte utilizamos o método `QCTraceSimulator.GetMetric` para obter o número de qubits atribuídos, bem como o número de qubits que o Controlled recebeu como `X` entrada.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="6d0d3-114">Finalmente, para obter todas as estatísticas recolhidas por contador de largura no formato CSV podemos utilizar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6d0d3-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="6d0d3-115">Ver também</span><span class="sxs-lookup"><span data-stu-id="6d0d3-115">See also</span></span> ##

- <span data-ttu-id="6d0d3-116">A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.</span><span class="sxs-lookup"><span data-stu-id="6d0d3-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
