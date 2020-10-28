---
uid: Microsoft.Quantum.Arrays.Exclude
title: Excluir função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719279"
---
# <a name="exclude-function"></a>Excluir função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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