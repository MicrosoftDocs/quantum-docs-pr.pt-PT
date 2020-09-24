---
title: Simuladores quânticos e programas Q#
description: Descreve os simuladores quânticos disponíveis como máquinas de destino para programas Q#.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a2a4bb829301f9db9bd14f3240556a403b9a54f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833431"
---
# <a name="quantum-simulators"></a><span data-ttu-id="56786-103">Simuladores quânticos</span><span class="sxs-lookup"><span data-stu-id="56786-103">Quantum simulators</span></span>

<span data-ttu-id="56786-104">Os simuladores quânticos são programas de software que funcionam em computadores clássicos e que atuam como o *computador de destino* de um programa Q#, possibilitando a execução e a testagem de programas quânticos num ambiente que prevê a reação dos qubits a diferentes operações.</span><span class="sxs-lookup"><span data-stu-id="56786-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="56786-105">Este artigo descreve que simuladores quânticos estão incluídos no Quantum Development kit (QDK) e as várias formas através das quais pode transmitir um programa Q# para os simuladores quânticos, como, por exemplo, com a linha de comandos ou com código de controlador escrito numa linguagem clássica.</span><span class="sxs-lookup"><span data-stu-id="56786-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="56786-106">Os simuladores do Quantum Development kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="56786-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="56786-107">O simulador quântico é responsável por fornecer implementações de primitivos quânticos para um algoritmo.</span><span class="sxs-lookup"><span data-stu-id="56786-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="56786-108">Essas implementações incluem operações primitivas como `H`, `CNOT` e `Measure`, bem como gestão e monitorização de qubits.</span><span class="sxs-lookup"><span data-stu-id="56786-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="56786-109">O QDK inclui diferentes classes de simuladores quânticos que representam modelos de execução distintos para o mesmo algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="56786-109">The QDK includes different classes of quantum simulators representing different run models for the same quantum algorithm.</span></span> 


<span data-ttu-id="56786-110">Cada tipo de simulador quântico pode fornecer diferentes implementações desses primitivos.</span><span class="sxs-lookup"><span data-stu-id="56786-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="56786-111">Por exemplo, o [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator) executa o algoritmo quântico ao simular na íntegra o [vetor de estado quântico](xref:microsoft.quantum.glossary#quantum-state), ao passo que o [simulador de rastreio de computador quântico](xref:microsoft.quantum.machines.qc-trace-simulator.intro) não tem minimamente em conta o estado quântico atual.</span><span class="sxs-lookup"><span data-stu-id="56786-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="56786-112">Em vez disso, rastreia a porta, o qubit e outras utilizações dos recursos para o algoritmo.</span><span class="sxs-lookup"><span data-stu-id="56786-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="56786-113">Classes de computadores quânticos</span><span class="sxs-lookup"><span data-stu-id="56786-113">Quantum machine classes</span></span>

<span data-ttu-id="56786-114">No futuro, o QDK irá definir classes adicionais de computadores quânticos para suportar outros tipos de simulações e para suportar a execução em hardware quântico.</span><span class="sxs-lookup"><span data-stu-id="56786-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support running on quantum hardware.</span></span> <span data-ttu-id="56786-115">Permitir que o algoritmo se mantenha constante enquanto se varia a implementação do computador subjacente facilita testar e depurar um algoritmo na simulação e, em seguida, executá-lo em hardware real com a confiança de que o algoritmo não mudou.</span><span class="sxs-lookup"><span data-stu-id="56786-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="56786-116">O QDK inclui várias classes de computadores quânticos, todas definidas no espaço de nomes `Microsoft.Quantum.Simulation.Simulators`.</span><span class="sxs-lookup"><span data-stu-id="56786-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="56786-117">Simulador</span><span class="sxs-lookup"><span data-stu-id="56786-117">Simulator</span></span> |<span data-ttu-id="56786-118">Classe</span><span class="sxs-lookup"><span data-stu-id="56786-118">Class</span></span>|<span data-ttu-id="56786-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="56786-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="56786-120">Simulador de estado completo</span><span class="sxs-lookup"><span data-stu-id="56786-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="56786-121">Executa e depura os algoritmos quânticos e está limitado a cerca de 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="56786-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="56786-122">Avaliador de recursos simples</span><span class="sxs-lookup"><span data-stu-id="56786-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="56786-123">Realiza uma análise de nível superior dos recursos necessários para executar um algoritmo quântico e suporta milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="56786-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="56786-124">Avaliador de recursos com base em rastreio</span><span class="sxs-lookup"><span data-stu-id="56786-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="56786-125">Executa uma análise avançada dos consumos de recursos para todo o grafo de chamada do algoritmo e suporta milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="56786-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="56786-126">Simulador Toffoli</span><span class="sxs-lookup"><span data-stu-id="56786-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="56786-127">Simula os algoritmos quânticos que estão limitados a operações quânticas `X`, `CNOT` e multicontroladas `X` e suporta milhões de qubits.</span><span class="sxs-lookup"><span data-stu-id="56786-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="56786-128">Invocar o simulador quântico</span><span class="sxs-lookup"><span data-stu-id="56786-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="56786-129">Em [Formas de executar programas Q#](xref:microsoft.quantum.guide.host-programs), são demonstradas três formas de transmitir o código Q# ao simulador quântico:</span><span class="sxs-lookup"><span data-stu-id="56786-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="56786-130">Através da linha de comandos</span><span class="sxs-lookup"><span data-stu-id="56786-130">Using the command line</span></span>
* <span data-ttu-id="56786-131">Através de um programa anfitrião Python</span><span class="sxs-lookup"><span data-stu-id="56786-131">Using a Python host program</span></span>
* <span data-ttu-id="56786-132">Através de um programa anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="56786-132">Using a C# host program</span></span>

<span data-ttu-id="56786-133">Os computadores quânticos são instâncias de classes .NET normais, por isso, são criados ao invocar o construtor, como em qualquer classe .NET.</span><span class="sxs-lookup"><span data-stu-id="56786-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="56786-134">A forma como o faz depende de como o programa Q# é executado.</span><span class="sxs-lookup"><span data-stu-id="56786-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56786-135">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="56786-135">Next steps</span></span>

* <span data-ttu-id="56786-136">Para obter detalhes relativos à invocação de computadores de destino para programas Q# em diferentes ambientes, veja [Formas de executar programas Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="56786-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
