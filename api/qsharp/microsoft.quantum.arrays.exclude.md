---
uid: Microsoft.Quantum.Arrays.Exclude
title: Excluir função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848665"
---
# <a name="exclude-function"></a>Excluir função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma matriz contendo os elementos de outra matriz, excluindo elementos numa determinada lista de índices.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="remove--int"></a>remover: [Int](xref:microsoft.quantum.lang-ref.int)[]

Um conjunto de índices que denotam quais os elementos que devem ser excluídos da saída.


### <a name="array--t"></a>matriz : 'T[]

Matriz dos quais são tomados os valores na matriz de saída.



## <a name="output--t"></a>Saída : 'T].

Um conjunto `output` tal que é o primeiro elemento de cujo índice não aparece em , tal que `output[0]` é o segundo `array` `remove` `output[1]` elemento, e assim por diante.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos de matriz.

## <a name="example"></a>Exemplo

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```