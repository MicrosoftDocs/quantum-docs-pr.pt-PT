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
# <a name="_swapordertopermutearray-function"></a>função _SwapOrderToPermuteArray

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve os elementos de ordem numa matriz que deve ser trocado para produzir uma matriz ordenada.
Pressupõe que as trocas ocorrem no lugar.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Entrada

### <a name="neworder--int"></a>newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz com a permutação dos índices da nova matriz. Deve haver elementos $n$, sendo cada um um inteiro único de $0$ a $n-1$.



## <a name="output--intint"></a>Saída :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]

A tuple representa os dois índices a serem trocados. Os swaps começam no índice mais baixo.

## <a name="example"></a>Exemplo

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Observações

## <a name="psuedocode"></a>Psuedocode

para (índice em 0..Length (newOrder) - 1) { enquanto newOrder[index] != index {Switch newOrder[index] com newOrder[newOrder[index]} }