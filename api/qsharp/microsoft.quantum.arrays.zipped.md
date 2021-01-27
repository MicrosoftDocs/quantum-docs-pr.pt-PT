---
uid: Microsoft.Quantum.Arrays.Zipped
title: Função com fecho
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845339"
---
# <a name="zipped-function"></a>Função com fecho

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Entrada

### <a name="left--t"></a>esquerda : 'T[]

Uma matriz contendo valores para o primeiro elemento de cada tuple.


### <a name="right--u"></a>direito : 'U[]

Uma matriz contendo valores para o segundo elemento de cada tuple.



## <a name="output--tu"></a>Saída : ('T,'U)[]

Uma matriz contendo pares da forma `(left[idx], right[idx])` para cada `idx` um . Se as duas matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos da matriz esquerda.
### <a name="u"></a>'U

O tipo de elementos de matriz certos.

## <a name="example"></a>Exemplo

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft.Quantum.Arrays.Unzipped](xref:Microsoft.Quantum.Arrays.Unzipped)