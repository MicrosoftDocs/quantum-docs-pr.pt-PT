---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Função FlatMapped
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719254"
---
# <a name="flatmapped-function"></a>Função FlatMapped

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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