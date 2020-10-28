---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: função _SwapOrderToPermuteArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719494"
---
# <a name="_swapordertopermutearray-function"></a>função _SwapOrderToPermuteArray

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Observações

## <a name="psuedocode"></a>Psuedocode

para (índice em 0..Length (newOrder) - 1) { enquanto newOrder[index] != index {Switch newOrder[index] com newOrder[newOrder[index]} } } } } } }