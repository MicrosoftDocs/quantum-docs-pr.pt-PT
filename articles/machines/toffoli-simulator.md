---
title: Kit de desenvolvimento do Quantum Toffoli simulador | Microsoft Docs
description: Visão geral do Toffoli Simulator do kit de desenvolvimento do quantum da Microsoft
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442359"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="af041-103">Kit de desenvolvimento do Quantum Toffoli simulador</span><span class="sxs-lookup"><span data-stu-id="af041-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="af041-104">O kit de desenvolvimento Quantum fornece um simulador de Toffoli, que é um simulador de finalidade especial que pode simular algoritmos de Quantum que são limitados a operações de Quantum x, CNOT e X com vários controle (toda a lógica clássica e cálculos estão disponíveis).</span><span class="sxs-lookup"><span data-stu-id="af041-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="af041-105">Embora o simulador de Toffoli seja muito mais restrito em operação do que o [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), ele pode simular muito mais qubits.</span><span class="sxs-lookup"><span data-stu-id="af041-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="af041-106">O simulador de Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo geralmente é limitado a cerca de 30.</span><span class="sxs-lookup"><span data-stu-id="af041-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="af041-107">Ele pode executar e depurar um conjunto limitado de algoritmos de Quantum escritos em Q # no seu computador; por exemplo, os Oracle que avaliam funções booleanas podem ser implementadas usando essas Gates e, portanto, são testadas para variar um grande número de qubits usando esse simulador.</span><span class="sxs-lookup"><span data-stu-id="af041-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="af041-108">Esse simulador Quantum é exposto por meio da classe `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="af041-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="af041-109">Para usar o simulador, basta criar uma instância dessa classe e passá-la para o método `Run` da operação Quantum que você deseja executar junto com o restante dos parâmetros:</span><span class="sxs-lookup"><span data-stu-id="af041-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="af041-110">Outras operações</span><span class="sxs-lookup"><span data-stu-id="af041-110">Other Operations</span></span>

<span data-ttu-id="af041-111">O `ToffoliSimulator` dá suporte a rotações e exponenciação Paulis, como `R` e `Exp`, quando a operação resultante é igual a `X` ou à identidade.</span><span class="sxs-lookup"><span data-stu-id="af041-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="af041-112">Há suporte para medição e Assert, mas apenas na base do Pauli `Z`.</span><span class="sxs-lookup"><span data-stu-id="af041-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="af041-113">Observe que a probabilidade de alguma medida é sempre 0 ou 1; Não há aleatoriedade no simulador de Toffoli.</span><span class="sxs-lookup"><span data-stu-id="af041-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="af041-114">Há suporte para `DumpMachine` e `DumpRegister`.</span><span class="sxs-lookup"><span data-stu-id="af041-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="af041-115">Ambos geram o estado de base `Z`atual de cada qubit, um qubit por linha.</span><span class="sxs-lookup"><span data-stu-id="af041-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="af041-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="af041-116">QubitCount</span></span>

<span data-ttu-id="af041-117">Por padrão, a `ToffoliSimulator` aloca espaço para 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="af041-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="af041-118">Se o algoritmo exigir mais do que isso, você poderá alterar a contagem de qubit fornecendo um valor para o parâmetro `qubitCount` para o construtor.</span><span class="sxs-lookup"><span data-stu-id="af041-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="af041-119">Cada qubit adicional requer um byte adicional de memória, portanto, não há nenhum custo significativo para a estimativa do número de qubits que você precisará.</span><span class="sxs-lookup"><span data-stu-id="af041-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="af041-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="af041-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
