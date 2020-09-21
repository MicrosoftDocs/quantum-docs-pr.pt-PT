---
title: Contador de largura - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o contador de largura do Microsoft QDK, que utiliza o simulador de traços Quânticos para contar o número de qubits atribuídos e emprestados por operações num Q# programa.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835949"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="e2cfb-103">Simulador de vestígios quânticos: contador de largura</span><span class="sxs-lookup"><span data-stu-id="e2cfb-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="e2cfb-104">O contador de largura faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="e2cfb-105">Pode usá-lo para contar o número de qubits atribuídos e emprestados por cada operação num Q# programa.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="e2cfb-106">Algumas operações primitivas podem alocar qubits extra, por exemplo, multiplicar operações controladas `X` ou `T` operações controladas.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="e2cfb-107">Invocando o contador de largura</span><span class="sxs-lookup"><span data-stu-id="e2cfb-107">Invoking the width counter</span></span>

<span data-ttu-id="e2cfb-108">Para executar o simulador de traços quânticos com o contador de largura, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UseWidthCounter` propriedade para **verdade**, e, em seguida, criar um novo caso com o como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="e2cfb-109">Usando o contador de largura num programa de anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="e2cfb-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="e2cfb-110">O exemplo C# que se segue nesta secção calcula o número de qubits extra atribuídos pela implementação de uma operação controlada por <xref:microsoft.quantum.intrinsic.x> multiplicação, com base no seguinte código de Q# amostra:</span><span class="sxs-lookup"><span data-stu-id="e2cfb-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="e2cfb-111">A operação controlada por multiplicação <xref:microsoft.quantum.intrinsic.x> atua num total de cinco qubits, atribui dois [qubits auxiliares,](xref:microsoft.quantum.glossary#ancilla)e tem uma largura de entrada de **5**.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="e2cfb-112">Utilize o seguinte programa C# para verificar as contagens:</span><span class="sxs-lookup"><span data-stu-id="e2cfb-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="e2cfb-113">A primeira parte do programa executa a `ApplyMultiControlledX` operação.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="e2cfb-114">A segunda parte utiliza o [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar o número de qubits atribuídos, bem como o número de qubits que a `Controlled X` operação recebeu como entrada.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="e2cfb-115">Finalmente, pode descodutar todas as estatísticas recolhidas pelo contador de largura em formato CSV utilizando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2cfb-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="e2cfb-116">Ver também</span><span class="sxs-lookup"><span data-stu-id="e2cfb-116">See also</span></span>

- <span data-ttu-id="e2cfb-117">A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="e2cfb-118">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="e2cfb-119">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="e2cfb-120">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> referência da API.</span><span class="sxs-lookup"><span data-stu-id="e2cfb-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
