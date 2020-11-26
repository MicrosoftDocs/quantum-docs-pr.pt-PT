---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Função MappedOverRange
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220693"
---
# <a name="mappedoverrange-function"></a>Função MappedOverRange

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um intervalo e uma função que toma um inteiro como entrada, devolve uma nova matriz que consiste nas imagens dos valores de gama sob a função.

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="mapper--int---t"></a>mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T

Uma função disso `Int` `'T` é usada para mapear valores de alcance.


### <a name="range--range"></a>gama : [Gama](xref:microsoft.quantum.lang-ref.range)

Uma série de inteiros.



## <a name="output--t"></a>Saída : 'T].

Uma matriz `'T[]` de elementos que são mapeados pela `mapper` função.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de resultado da `mapper` função.

## <a name="remarks"></a>Observações

A função é definida para tipos genéricos, ou seja, sempre que temos uma função `mapper: Int -> 'T` podemos mapear os valores da gama e produzir uma matriz de tipo `'T[]` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Mapeado](xref:Microsoft.Quantum.Arrays.Mapped)