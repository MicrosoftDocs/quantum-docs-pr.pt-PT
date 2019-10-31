---
title: Simulador de rastreio do computador quântico | Microsoft Docs
description: Descrição geral do simulador de rastreio do computador quântico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035124"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="9ce35-103">Simulador de Rastreio Quântico</span><span class="sxs-lookup"><span data-stu-id="9ce35-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="9ce35-104">O simulador de rastreio do computador quântico da Microsoft executa um programa quântico sem simular verdadeiramente o estado de um computador quântico.</span><span class="sxs-lookup"><span data-stu-id="9ce35-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="9ce35-105">Por esse motivo, o simulador de rastreio pode executar programas quânticos que utilizam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="9ce35-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="9ce35-106">É útil para duas finalidades principais:</span><span class="sxs-lookup"><span data-stu-id="9ce35-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="9ce35-107">Depuração de código clássico que faz parte de um programa quântico.</span><span class="sxs-lookup"><span data-stu-id="9ce35-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="9ce35-108">Estimativa dos recursos necessários para executar uma determinada instância de um programa quântico num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="9ce35-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="9ce35-109">O simulador de rastreio recorre a informações adicionais fornecidas pelo utilizador quando têm de ser executadas medições.</span><span class="sxs-lookup"><span data-stu-id="9ce35-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="9ce35-110">Veja a secção [Fornecer a probabilidade de resultados de medição](#providing-the-probability-of-measurement-outcomes) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9ce35-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="9ce35-111">Fornecer a Probabilidade de Resultados de Medição</span><span class="sxs-lookup"><span data-stu-id="9ce35-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="9ce35-112">Existem dois tipos de medições que aparecem em algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="9ce35-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="9ce35-113">O primeiro tipo desempenha uma função auxiliar, na qual o utilizador costuma saber a probabilidade dos resultados.</span><span class="sxs-lookup"><span data-stu-id="9ce35-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="9ce35-114">Neste caso, o utilizador pode escrever <xref:microsoft.quantum.primitive.assertprob> no espaço de nomes <xref:microsoft.quantum.primitive> para expressar esse mesmo conhecimento.</span><span class="sxs-lookup"><span data-stu-id="9ce35-114">In this case the user can write <xref:microsoft.quantum.primitive.assertprob> from the <xref:microsoft.quantum.primitive> namespace to express this knowledge.</span></span> <span data-ttu-id="9ce35-115">O exemplo seguinte ilustra isso mesmo:</span><span class="sxs-lookup"><span data-stu-id="9ce35-115">The following example illustrates this:</span></span>

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

<span data-ttu-id="9ce35-116">Quando o simulador de rastreio executar `AssertProb`, vai registar que a medição de `PauliZ` em `source` e `ancilla` deve receber um resultado de `Zero` com uma probabilidade de 0,5.</span><span class="sxs-lookup"><span data-stu-id="9ce35-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `ancilla` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="9ce35-117">Quando o simulador executar `M` mais tarde, detetará que os valores registados das probabilidades de resultado e `M` devolverão `Zero` ou `One` com uma probabilidade de 0,5.</span><span class="sxs-lookup"><span data-stu-id="9ce35-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="9ce35-118">Quando o mesmo código for executado num simulador que monitoriza o estado quântico, esse simulador verificará se as probabilidades fornecidas em `AssertProb` estão corretas.</span><span class="sxs-lookup"><span data-stu-id="9ce35-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="9ce35-119">Executar o Programa com o Simulador de Rastreio do Computador Quântico</span><span class="sxs-lookup"><span data-stu-id="9ce35-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="9ce35-120">O simulador de rastreio do computador quântico pode ser visualizado tal como outro computador de destino.</span><span class="sxs-lookup"><span data-stu-id="9ce35-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="9ce35-121">O programa do controlador C# para o utilizar é muito semelhante ao de qualquer outro Simulador quântico:</span><span class="sxs-lookup"><span data-stu-id="9ce35-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="9ce35-122">Note que, se houver pelo menos uma medição não anotada com `AssertProb`, o simulador lançará `UnconstrainedMeasurementException` a partir do espaço de nomes `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`.</span><span class="sxs-lookup"><span data-stu-id="9ce35-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="9ce35-123">Veja a documentação da API em [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9ce35-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="9ce35-124">Além de executar programas quânticos, o simulador de rastreio inclui cinco componentes para detetar erros em programas e executar estimativas de recursos de programas quânticos:</span><span class="sxs-lookup"><span data-stu-id="9ce35-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="9ce35-125">Verificador de Entradas Distintas</span><span class="sxs-lookup"><span data-stu-id="9ce35-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="9ce35-126">Verificador de Utilização de Qubits Invalidados</span><span class="sxs-lookup"><span data-stu-id="9ce35-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="9ce35-127">Contador de Operações Primitivas</span><span class="sxs-lookup"><span data-stu-id="9ce35-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="9ce35-128">Contador de Profundidade de Circuitos</span><span class="sxs-lookup"><span data-stu-id="9ce35-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="9ce35-129">Contador de Largura de Circuitos</span><span class="sxs-lookup"><span data-stu-id="9ce35-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="9ce35-130">Cada um destes componentes pode ser ativado ao definir os sinalizadores adequados em `QCTraceSimulatorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="9ce35-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="9ce35-131">Mais detalhes sobre como utilizar cada um desses componentes são fornecidos nos ficheiros de referência correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9ce35-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="9ce35-132">Veja a documentação da API sobre [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obter detalhes específicos.</span><span class="sxs-lookup"><span data-stu-id="9ce35-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ce35-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9ce35-133">See also</span></span>
<span data-ttu-id="9ce35-134">Referência C# do [simulador de rastreio](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) do computador quântico</span><span class="sxs-lookup"><span data-stu-id="9ce35-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

