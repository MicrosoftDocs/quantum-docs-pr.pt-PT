---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Função FlatMapped
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221254"
---
# <a name="flatmapped-function"></a>Função FlatMapped

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma matriz e uma função que mapeiam um elemento de matriz para alguma matriz de saída, devolve as matrizes de saída concatenated para cada elemento de matriz.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Entrada

### <a name="mapper--tinput---toutput"></a>mapper : 'TInput -> 'TOutput[]

Uma função disso `'TInput` `'TOutput[]` é usada para mapear elementos de matriz.


### <a name="array--tinput"></a>matriz : 'TInput[]

Uma variedade de elementos.



## <a name="output--toutput"></a>Saída : 'TOutput[]

Uma matriz da `'TOutput[]` qual é a concatenação de todas as matrizes geradas pela função de mapeamento.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="tinput"></a>'TInput

O tipo de `array` elementos.
### <a name="toutput"></a>'TOutput

A `mapper` função retorna os conjuntos deste tipo.