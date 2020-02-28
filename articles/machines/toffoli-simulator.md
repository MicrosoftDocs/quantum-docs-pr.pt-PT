---
title: Simulador de Kit de Desenvolvimento Quântico Toffoli
description: Saiba mais sobre o Microsoft QDK Toffoli Simulator, um simulador quântico de propósito especial que pode ser usado com milhões de qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907023"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="cb819-103">Simulador de Kit de Desenvolvimento Quântico Toffoli</span><span class="sxs-lookup"><span data-stu-id="cb819-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="cb819-104">O Kit de Desenvolvimento Quântico fornece um simulador Toffoli, que é um simulador de propósito especial que pode simular algoritmos quânticos que estão limitados a Operações Quânticas X, CNOT e multi-controladas (todas as lógicas clássicas e computações estão disponíveis).</span><span class="sxs-lookup"><span data-stu-id="cb819-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="cb819-105">Embora o simulador Toffoli seja muito mais restrito em funcionamento do que todo o [simulador de estado,](xref:microsoft.quantum.machines.full-state-simulator)pode simular muito mais qubits.</span><span class="sxs-lookup"><span data-stu-id="cb819-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="cb819-106">O simulador Toffoli pode ser usado com milhões de qubits, enquanto o simulador de estado completo é geralmente limitado a cerca de 30.</span><span class="sxs-lookup"><span data-stu-id="cb819-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="cb819-107">Pode executar e depurar um conjunto limitado de algoritmos quânticos escritos em Q# no seu computador; por exemplo, os oráculos que avaliam as funções booleanas podem ser implementados usando estes portões e assim testados em grande número de qubits usando este simulador.</span><span class="sxs-lookup"><span data-stu-id="cb819-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="cb819-108">Este simulador quântico é exposto através da classe `ToffoliSimulator`.</span><span class="sxs-lookup"><span data-stu-id="cb819-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="cb819-109">Para utilizar o simulador, basta criar uma instância desta classe e passá-la para o método `Run` da operação quântica que pretende executar juntamente com o resto dos parâmetros:</span><span class="sxs-lookup"><span data-stu-id="cb819-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="cb819-110">Outras Operações</span><span class="sxs-lookup"><span data-stu-id="cb819-110">Other Operations</span></span>

<span data-ttu-id="cb819-111">O `ToffoliSimulator` suporta rotações e Paulis exponenciados, como `R` e `Exp`, quando a operação resultante é igual a `X` ou à identidade.</span><span class="sxs-lookup"><span data-stu-id="cb819-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="cb819-112">A medição e a afirmação são suportadas, mas apenas na base pauli `Z`.</span><span class="sxs-lookup"><span data-stu-id="cb819-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="cb819-113">Note que a probabilidade de alguma medição é sempre 0 ou 1; não há aleatoriedade no simulador de Toffoli.</span><span class="sxs-lookup"><span data-stu-id="cb819-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="cb819-114">`DumpMachine` e `DumpRegister` são apoiados.</span><span class="sxs-lookup"><span data-stu-id="cb819-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="cb819-115">Ambos eles outputam o estado atual `Z`-base de cada qubit, um qubit por linha.</span><span class="sxs-lookup"><span data-stu-id="cb819-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="cb819-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="cb819-116">QubitCount</span></span>

<span data-ttu-id="cb819-117">Por predefinição, o `ToffoliSimulator` atribui espaço para 65.536 qubits.</span><span class="sxs-lookup"><span data-stu-id="cb819-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="cb819-118">Se o seu algoritmo necessitar de mais do que isso, pode alterar a contagem de qubit fornecendo um valor para o parâmetro `qubitCount` para o construtor.</span><span class="sxs-lookup"><span data-stu-id="cb819-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="cb819-119">Cada qubit adicional requer um byte adicional de memória, por isso não há um custo significativo para sobrestimar o número de qubits que você precisará.</span><span class="sxs-lookup"><span data-stu-id="cb819-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="cb819-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cb819-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
