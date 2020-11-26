---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Função Zipped4
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219639"
---
# <a name="zipped4-function"></a>Função Zipped4

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado quatro matrizes, devolve uma nova matriz de 4 tuples de modo que cada 4 tuple contém um elemento de cada matriz original.

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>Entrada

### <a name="first--t1"></a>primeiro : 'T1].

Uma matriz contendo valores para o primeiro elemento de cada tuple.


### <a name="second--t2"></a>segundo : 'T2]]

Uma matriz contendo valores para o segundo elemento de cada tuple.


### <a name="third--t3"></a>terceiro: 'T3]]

Uma matriz contendo valores para o terceiro elemento de cada tuple.


### <a name="fourth--t4"></a>quarto : 'T4]]

Uma matriz contendo valores para o quarto elemento de cada tuple.



## <a name="output--t1t2t3t4"></a>Saída: ('T1,'T2,'T3,'T4)[]

Uma matriz contendo 4 tuples da forma `(first[idx], second[idx], third[idx], fourth[idx])` para cada `idx` . Se as quatro matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t1"></a>'T1

O tipo de primeiros elementos de matriz.
### <a name="t2"></a>'T2

O tipo de elementos da segunda matriz.
### <a name="t3"></a>'T3

O tipo de elementos da terceira matriz.
### <a name="t4"></a>'T4

O tipo de elementos da quarta matriz.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)