---
title: Simulador de rastreio quântico - Quantum Development kit
description: Aprenda a utilizar o simulador de rastreio de computador quântico da Microsoft para depurar código clássico e para calcular os requisitos de recursos de um programa Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: c01f01973ea08153cbfa35d87a588a4eae46f1b7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871115"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="d76ac-103">Simulador de rastreio quântico do Microsoft Quantum Development kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="d76ac-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="d76ac-104">A classe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> do QDK executa um programa quântico sem, na realidade, simular o estado de um computador quântico.</span><span class="sxs-lookup"><span data-stu-id="d76ac-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="d76ac-105">Por esse motivo, o simulador de rastreio quântico pode executar programas quânticos que utilizam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="d76ac-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="d76ac-106">É útil para duas finalidades principais:</span><span class="sxs-lookup"><span data-stu-id="d76ac-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="d76ac-107">Depuração de código clássico que faz parte de um programa quântico.</span><span class="sxs-lookup"><span data-stu-id="d76ac-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="d76ac-108">Estimativa dos recursos necessários para executar uma determinada instância de um programa quântico num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="d76ac-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="d76ac-109">Na verdade, o [Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator), que oferece um conjunto de métricas mais limitado, foi concebido com base no simulador de rastreio.</span><span class="sxs-lookup"><span data-stu-id="d76ac-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="d76ac-110">Invocar o simulador de rastreio quântico</span><span class="sxs-lookup"><span data-stu-id="d76ac-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="d76ac-111">Pode utilizar o simulador de rastreio quântico para executar qualquer operação Q#.</span><span class="sxs-lookup"><span data-stu-id="d76ac-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="d76ac-112">Tal como sucede com outros computadores de destino, vai criar primeiro uma instância da classe `QCTraceSimulator` e, depois, transmiti-la como o primeiro parâmetro do método `Run` de uma operação.</span><span class="sxs-lookup"><span data-stu-id="d76ac-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="d76ac-113">Tenha em conta que, ao contrário da classe `QuantumSimulator`, a classe `QCTraceSimulator` não implementa a interface <xref:System.IDisposable>, pelo que não precisa de a incluir dentro de uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="d76ac-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="d76ac-114">Fornecer a probabilidade de resultados de medições</span><span class="sxs-lookup"><span data-stu-id="d76ac-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="d76ac-115">Uma vez que o simulador de rastreio quântico não simula o estado quântico em si, não pode calcular a probabilidade de resultados de medições numa operação.</span><span class="sxs-lookup"><span data-stu-id="d76ac-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="d76ac-116">Consequentemente, se uma operação incluir medições, tem de fornecer explicitamente essas probabilidades com a operação <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> a partir do espaço de nomes <xref:microsoft.quantum.diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="d76ac-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="d76ac-117">O exemplo seguinte ilustra isso mesmo:</span><span class="sxs-lookup"><span data-stu-id="d76ac-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="d76ac-118">Quando o simulador de rastreio quântico encontrar `AssertMeasurementProbability`, regista que a medição `PauliZ` em `source` e em `q` deverá produzir o resultado `Zero`, com a probabilidade de **0,5**.</span><span class="sxs-lookup"><span data-stu-id="d76ac-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="d76ac-119">Quando executa a operação `M` mais tarde, localiza os valores registados das probabilidades dos resultados e `M` devolve `Zero` ou `One`, com a probabilidade de **0,5**.</span><span class="sxs-lookup"><span data-stu-id="d76ac-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="d76ac-120">Quando o mesmo código for executado num simulador que rastreia o estado quântico, esse simulador verificará se as probabilidades fornecidas em `AssertMeasurementProbability` estão corretas.</span><span class="sxs-lookup"><span data-stu-id="d76ac-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="d76ac-121">Note que, se houver pelo menos uma operação de medição não anotada com `AssertMeasurementProbability`, o simulador emitirá [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span><span class="sxs-lookup"><span data-stu-id="d76ac-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="d76ac-122">Ferramentas do simulador de rastreio quântico</span><span class="sxs-lookup"><span data-stu-id="d76ac-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="d76ac-123">O QDK inclui cinco ferramentas que pode utilizar com o simulador de rastreio quântico para detetar erros nos seus programas e realizar estimativas de recursos dos programas quânticos:</span><span class="sxs-lookup"><span data-stu-id="d76ac-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="d76ac-124">Ferramenta</span><span class="sxs-lookup"><span data-stu-id="d76ac-124">Tool</span></span> | <span data-ttu-id="d76ac-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="d76ac-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="d76ac-126">Verificador de entradas distintas</span><span class="sxs-lookup"><span data-stu-id="d76ac-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="d76ac-127">Verifica potenciais conflitos com qubits partilhados</span><span class="sxs-lookup"><span data-stu-id="d76ac-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="d76ac-128">Verificador de utilização de qubits invalidados</span><span class="sxs-lookup"><span data-stu-id="d76ac-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="d76ac-129">Verifica se o programa aplica uma operação a um qubit que já foi lançado</span><span class="sxs-lookup"><span data-stu-id="d76ac-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="d76ac-130">Contador de operações primitivas</span><span class="sxs-lookup"><span data-stu-id="d76ac-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="d76ac-131">Conta o número de execuções primitivas que todas as operações invocadas num programa quântico utilizaram</span><span class="sxs-lookup"><span data-stu-id="d76ac-131">Counts the number of primitive executions used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="d76ac-132">Contador de profundidade</span><span class="sxs-lookup"><span data-stu-id="d76ac-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="d76ac-133">Recolhe contagens que representam o limite inferior da profundidade de todas as operações invocadas num programa quântico</span><span class="sxs-lookup"><span data-stu-id="d76ac-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="d76ac-134">Contador de largura</span><span class="sxs-lookup"><span data-stu-id="d76ac-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="d76ac-135">Conta o número de qubits alocados e emprestados por cada operação num programa quântico</span><span class="sxs-lookup"><span data-stu-id="d76ac-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="d76ac-136">Para ativar cada uma destas ferramentas, defina os sinalizadores correspondentes em `QCTraceSimulatorConfiguration` e transmita a configuração para a declaração `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="d76ac-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="d76ac-137">Para obter informações sobre a utilização de cada uma das ferramentas, veja as ligações na lista anterior.</span><span class="sxs-lookup"><span data-stu-id="d76ac-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="d76ac-138">Para obter mais informações sobre a configuração de `QCTraceSimulator`, veja [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d76ac-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="d76ac-139">Métodos QCTraceSimulator</span><span class="sxs-lookup"><span data-stu-id="d76ac-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="d76ac-140">O `QCTraceSimulator` tem diversos métodos incorporados para obter os valores das métricas rastreadas durante uma operação quântica.</span><span class="sxs-lookup"><span data-stu-id="d76ac-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="d76ac-141">Podem ser encontrados exemplos dos métodos [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) e [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) nos artigos [Contador de operações primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Contador de profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) e [Contador de largura](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="d76ac-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="d76ac-142">Para obter informações relativas a todos os métodos disponíveis, veja [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) na referência da API de Q#.</span><span class="sxs-lookup"><span data-stu-id="d76ac-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d76ac-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d76ac-143">See also</span></span>

- [<span data-ttu-id="d76ac-144">Avaliador de recursos quânticos</span><span class="sxs-lookup"><span data-stu-id="d76ac-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="d76ac-145">Simulador Toffoli quântico</span><span class="sxs-lookup"><span data-stu-id="d76ac-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="d76ac-146">Simulador de estado completo quântico</span><span class="sxs-lookup"><span data-stu-id="d76ac-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 