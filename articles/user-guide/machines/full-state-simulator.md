---
title: Simulador quântico de estado completo - Kit de Desenvolvimento Quântico
description: Aprenda a executar os seus Q# programas no simulador completo do Microsoft Quantum Development Kit.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: b15af66123dadae09815cde1966c69b3ce2e9e64
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868343"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="c08ec-103">Kit de Desenvolvimento Quântico (QDK) simulador de estado completo</span><span class="sxs-lookup"><span data-stu-id="c08ec-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="c08ec-104">O QDK fornece um simulador de estado completo que simula uma máquina quântica no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="c08ec-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="c08ec-105">Você pode usar o simulador de estado completo para executar e depurar algoritmos quânticos escritos em Q# , usando até 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="c08ec-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="c08ec-106">O simulador de estado completo é semelhante ao simulador quântico usado na plataforma [LIQ$Ui/rangle$](http://stationq.github.io/Liquid/) da Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="c08ec-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="c08ec-107">Invocando e executando o simulador de estado completo</span><span class="sxs-lookup"><span data-stu-id="c08ec-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="c08ec-108">Expões o simulador de estado completo através da `QuantumSimulator` aula.</span><span class="sxs-lookup"><span data-stu-id="c08ec-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="c08ec-109">Para mais detalhes, consulte [Formas de executar um Q# programa](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="c08ec-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="c08ec-110">Invocando o simulador de C #</span><span class="sxs-lookup"><span data-stu-id="c08ec-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="c08ec-111">Crie uma instância da `QuantumSimulator` classe e, em seguida, passe-a para o `Run` método de uma operação quântica, juntamente com quaisquer parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="c08ec-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="c08ec-112">Como a `QuantumSimulator` classe implementa a <xref:System.IDisposable> interface, deve ligar para o método `Dispose` uma vez que já não precisa da instância do simulador.</span><span class="sxs-lookup"><span data-stu-id="c08ec-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="c08ec-113">A melhor maneira de o fazer é embrulhar a declaração e as operações do simulador dentro de uma declaração [de utilização,](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) que automaticamente chama o `Dispose` método.</span><span class="sxs-lookup"><span data-stu-id="c08ec-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="c08ec-114">Invocando o simulador de Python</span><span class="sxs-lookup"><span data-stu-id="c08ec-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="c08ec-115">Utilizar o método [simulado da](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) Q# biblioteca Python com a operação importada: Q#</span><span class="sxs-lookup"><span data-stu-id="c08ec-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="c08ec-116">Invocando o simulador da linha de comando</span><span class="sxs-lookup"><span data-stu-id="c08ec-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="c08ec-117">Ao executar um Q# programa a partir da linha de comando, o simulador de estado completo é a máquina alvo predefinido.</span><span class="sxs-lookup"><span data-stu-id="c08ec-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="c08ec-118">Opcionalmente, pode utilizar o parâmetro **--simulador** (ou **atalho -s** para especificar a máquina-alvo desejada.</span><span class="sxs-lookup"><span data-stu-id="c08ec-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="c08ec-119">Ambos os comandos seguintes executam um programa utilizando o simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="c08ec-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="c08ec-120">Invocando o simulador dos Cadernos Juptyer</span><span class="sxs-lookup"><span data-stu-id="c08ec-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="c08ec-121">Use o comando mágico I Q# [%simular](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para executar a Q# operação.</span><span class="sxs-lookup"><span data-stu-id="c08ec-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="c08ec-122">Semear o simulador</span><span class="sxs-lookup"><span data-stu-id="c08ec-122">Seeding the simulator</span></span>

<span data-ttu-id="c08ec-123">Por predefinição, o simulador de estado completo utiliza um gerador de números aleatórios para simular aleatoriedade quântica.</span><span class="sxs-lookup"><span data-stu-id="c08ec-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="c08ec-124">Para efeitos de teste, por vezes é útil ter resultados determinísticos.</span><span class="sxs-lookup"><span data-stu-id="c08ec-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="c08ec-125">Num programa C# pode fazê-lo fornecendo uma semente para o gerador de números aleatórios no `QuantumSimulator` construtor através do `randomNumberGeneratorSeed` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="c08ec-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="c08ec-126">Fios de configuração</span><span class="sxs-lookup"><span data-stu-id="c08ec-126">Configuring threads</span></span>

<span data-ttu-id="c08ec-127">O simulador de estado completo utiliza [o OpenMP](http://www.openmp.org/) para paralelizar a álgebra linear necessária.</span><span class="sxs-lookup"><span data-stu-id="c08ec-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="c08ec-128">Por padrão, o OpenMP utiliza todos os fios de hardware disponíveis, o que significa que os programas com um pequeno número de qubits muitas vezes funcionam lentamente porque a coordenação que é necessária anãs o trabalho real.</span><span class="sxs-lookup"><span data-stu-id="c08ec-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="c08ec-129">Pode fixá-lo definindo a variável ambiente `OMP_NUM_THREADS` para um número pequeno.</span><span class="sxs-lookup"><span data-stu-id="c08ec-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="c08ec-130">Como regra geral do polegar, configuure um fio para até quatro qubits, e, em seguida, um fio adicional por qubit.</span><span class="sxs-lookup"><span data-stu-id="c08ec-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="c08ec-131">Pode ser necessário ajustar a variável dependendo do seu algoritmo.</span><span class="sxs-lookup"><span data-stu-id="c08ec-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="c08ec-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c08ec-132">See also</span></span>

- [<span data-ttu-id="c08ec-133">Avaliador de recursos quânticos</span><span class="sxs-lookup"><span data-stu-id="c08ec-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="c08ec-134">Simulador Toffoli quântico</span><span class="sxs-lookup"><span data-stu-id="c08ec-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="c08ec-135">Simulador de vestígios quânticos</span><span class="sxs-lookup"><span data-stu-id="c08ec-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)