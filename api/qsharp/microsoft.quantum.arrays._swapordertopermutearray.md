---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: função _SwapOrderToPermuteArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846297"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="c0e75-102">função _SwapOrderToPermuteArray</span><span class="sxs-lookup"><span data-stu-id="c0e75-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="c0e75-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c0e75-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c0e75-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0e75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0e75-105">Devolve os elementos de ordem numa matriz que deve ser trocado para produzir uma matriz ordenada.</span><span class="sxs-lookup"><span data-stu-id="c0e75-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="c0e75-106">Pressupõe que as trocas ocorrem no lugar.</span><span class="sxs-lookup"><span data-stu-id="c0e75-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c0e75-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0e75-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="c0e75-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c0e75-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c0e75-109">Matriz com a permutação dos índices da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="c0e75-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="c0e75-110">Deve haver elementos $n$, sendo cada um um inteiro único de $0$ a $n-1$.</span><span class="sxs-lookup"><span data-stu-id="c0e75-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="c0e75-111">Saída :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="c0e75-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c0e75-112">A tuple representa os dois índices a serem trocados.</span><span class="sxs-lookup"><span data-stu-id="c0e75-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="c0e75-113">Os swaps começam no índice mais baixo.</span><span class="sxs-lookup"><span data-stu-id="c0e75-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="c0e75-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c0e75-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="c0e75-115">Observações</span><span class="sxs-lookup"><span data-stu-id="c0e75-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="c0e75-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="c0e75-116">Psuedocode</span></span>

<span data-ttu-id="c0e75-117">para (índice em 0..Length (newOrder) - 1) { enquanto newOrder[index] != index {Switch newOrder[index] com newOrder[newOrder[index]} }</span><span class="sxs-lookup"><span data-stu-id="c0e75-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>