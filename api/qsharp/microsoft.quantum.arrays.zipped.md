---
uid: Microsoft.Quantum.Arrays.Zipped
title: Função com fecho
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718714"
---
# <a name="zipped-function"></a>Função com fecho

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft.Quantum.Arrays.Unzipped](xref:Microsoft.Quantum.Arrays.Unzipped)