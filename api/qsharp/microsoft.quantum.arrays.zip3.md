---
uid: Microsoft.Quantum.Arrays.Zip3
title: Função Zip3
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845358"
---
# <a name="zip3-function"></a>Função Zip3

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip3 foi depreciado. Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped3> em vez disso.

Tendo em conta três matrizes, devolve uma nova matriz de 3 tuples de modo a que cada 3 tuple contenha um elemento de cada matriz original.

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>Entrada

### <a name="first--t1"></a>primeiro : 'T1].

Uma matriz contendo valores para o primeiro elemento de cada tuple.


### <a name="second--t2"></a>segundo : 'T2]]

Uma matriz contendo valores para o segundo elemento de cada tuple.


### <a name="third--t3"></a>terceiro: 'T3]]

Uma matriz contendo valores para o terceiro elemento de cada tuple.



## <a name="output--t1t2t3"></a>Saída : ('T1,'T2,'T3)[]

Uma matriz contendo 3 tuples da forma `(first[idx], second[idx], third[idx])` para cada `idx` . Se as três matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t1"></a>'T1

O tipo de primeiros elementos de matriz.
### <a name="t2"></a>'T2

O tipo de elementos da segunda matriz.
### <a name="t3"></a>'T3

O tipo de elementos da terceira matriz.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)