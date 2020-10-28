---
title: Contador de largura - Kit de Desenvolvimento Quântico
description: 'Saiba mais sobre o contador de largura do Microsoft QDK, que utiliza o simulador de traços Quânticos para contar o número de qubits atribuídos e emprestados por operações num :::no-loc(Q#)::: programa.'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691123"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="be66b-103">Simulador de vestígios quânticos: contador de largura</span><span class="sxs-lookup"><span data-stu-id="be66b-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="be66b-104">O contador de largura faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="be66b-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="be66b-105">Pode usá-lo para contar o número de qubits atribuídos e emprestados por cada operação num :::no-loc(Q#)::: programa.</span><span class="sxs-lookup"><span data-stu-id="be66b-105">You can use it to count the number of qubits allocated and borrowed by each operation in a :::no-loc(Q#)::: program.</span></span> <span data-ttu-id="be66b-106">Algumas operações primitivas podem alocar qubits extra, por exemplo, multiplicar operações controladas `X` ou `T` operações controladas.</span><span class="sxs-lookup"><span data-stu-id="be66b-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="be66b-107">Invocando o contador de largura</span><span class="sxs-lookup"><span data-stu-id="be66b-107">Invoking the width counter</span></span>

<span data-ttu-id="be66b-108">Para executar o simulador de traços quânticos com o contador de largura, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UseWidthCounter` propriedade para **verdade** , e, em seguida, criar um novo caso com o como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="be66b-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="be66b-109">Usando o contador de largura num programa de anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="be66b-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="be66b-110">O exemplo C# que se segue nesta secção calcula o número de qubits extra atribuídos pela implementação de uma operação controlada por <xref:Microsoft.Quantum.Intrinsic.X> multiplicação, com base no seguinte código de :::no-loc(Q#)::: amostra:</span><span class="sxs-lookup"><span data-stu-id="be66b-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="be66b-111">A operação controlada por multiplicação <xref:Microsoft.Quantum.Intrinsic.X> atua num total de cinco qubits, atribui dois [qubits auxiliares,](xref:microsoft.quantum.glossary#ancilla)e tem uma largura de entrada de **5** .</span><span class="sxs-lookup"><span data-stu-id="be66b-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5** .</span></span> <span data-ttu-id="be66b-112">Utilize o seguinte programa C# para verificar as contagens:</span><span class="sxs-lookup"><span data-stu-id="be66b-112">Use the following C# program to verify the counts:</span></span>

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

<span data-ttu-id="be66b-113">A primeira parte do programa executa a `ApplyMultiControlledX` operação.</span><span class="sxs-lookup"><span data-stu-id="be66b-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="be66b-114">A segunda parte utiliza o [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar o número de qubits atribuídos, bem como o número de qubits que a `Controlled X` operação recebeu como entrada.</span><span class="sxs-lookup"><span data-stu-id="be66b-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="be66b-115">Finalmente, pode descodutar todas as estatísticas recolhidas pelo contador de largura em formato CSV utilizando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="be66b-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="be66b-116">Ver também</span><span class="sxs-lookup"><span data-stu-id="be66b-116">See also</span></span>

- <span data-ttu-id="be66b-117">A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="be66b-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="be66b-118">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.</span><span class="sxs-lookup"><span data-stu-id="be66b-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="be66b-119">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.</span><span class="sxs-lookup"><span data-stu-id="be66b-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="be66b-120">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> referência da API.</span><span class="sxs-lookup"><span data-stu-id="be66b-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
