---
uid: Microsoft.Quantum.Arrays.Zip
title: Função zip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850907"
---
# <a name="zip-function"></a>Função zip

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip foi depreciado. Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped> em vez disso.

Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft.Quantum.Arrays.Unzipped](xref:Microsoft.Quantum.Arrays.Unzipped)