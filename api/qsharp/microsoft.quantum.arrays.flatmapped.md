---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: Função FlatMapped
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848647"
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

## <a name="example"></a>Exemplo

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```