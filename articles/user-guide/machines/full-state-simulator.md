---
title: Simulador de Estado Completo
description: Saiba como executar os seus programas Q# no Microsoft Quantum Development Kit Full State Simulator.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275643"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="1ca6f-103">Kit de desenvolvimento quântico full state simulator</span><span class="sxs-lookup"><span data-stu-id="1ca6f-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="1ca6f-104">O Quantum Development Kit fornece um simulador quântico de estado completo semelhante ao [LIQ$Ui/rangle$](http://stationq.github.io/Liquid/) da Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="1ca6f-105">Este simulador pode ser usado para executar e depurar algoritmos quânticos escritos em Q# no seu computador.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="1ca6f-106">Este simulador quântico é exposto através da `QuantumSimulator` aula.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="1ca6f-107">Para utilizar o simulador, basta criar uma instância desta classe e passá-la para o `Run` método da operação quântica que pretende executar juntamente com o resto dos parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1ca6f-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="1ca6f-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="1ca6f-108">IDisposable</span></span>

<span data-ttu-id="1ca6f-109">A `QuantumSimulator` classe <xref:System.IDisposable> implementa, portanto, o `Dispose` método deve ser chamado uma vez que a instância do simulador não é mais usada.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="1ca6f-110">A melhor maneira de o fazer é embrulhar o simulador dentro de uma `using` declaração, como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="1ca6f-111">Sementes</span><span class="sxs-lookup"><span data-stu-id="1ca6f-111">Seed</span></span>

<span data-ttu-id="1ca6f-112">Usa `QuantumSimulator` um gerador de números aleatórios para simular aleatoriedade quântica.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="1ca6f-113">Para efeitos de teste, por vezes é útil ter resultados determinísticos.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="1ca6f-114">Isto pode ser conseguido fornecendo uma semente para o gerador de números aleatórios no `QuantumSimulator` construtor através do `randomNumberGeneratorSeed` parâmetro:</span><span class="sxs-lookup"><span data-stu-id="1ca6f-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="1ca6f-115">Fios</span><span class="sxs-lookup"><span data-stu-id="1ca6f-115">Threads</span></span>

<span data-ttu-id="1ca6f-116">Utiliza `QuantumSimulator` [OpenMP](http://www.openmp.org/) para paralelizar a álgebra linear necessária.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="1ca6f-117">Por predefinição, o OpenMP utiliza todos os threads de hardware disponíveis, o que significa que os programas com pequenos números de qubits serão normalmente executados lentamente, pois a coordenação necessária diminuirá o trabalho real.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="1ca6f-118">Isto pode ser corrigido definindo a variável ambiente `OMP_NUM_THREADS` para um número pequeno.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="1ca6f-119">Como regra geral muito superficial, um thread é bom para um máximo de quatro qubits e, em seguida, um thread adicional por qubit é bom, embora isto seja altamente dependente do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="1ca6f-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

