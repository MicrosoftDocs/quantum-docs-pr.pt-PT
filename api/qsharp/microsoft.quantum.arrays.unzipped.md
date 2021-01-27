---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Função desapertado
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845370"
---
# <a name="unzipped-function"></a>Função desapertado

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma matriz de 2 tuples, devolve um tuple de duas matrizes, cada uma contendo os elementos dos tuples da matriz de entrada.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Entrada

### <a name="arr--tu"></a>arr : ('T,'U)[]

Uma matriz contendo 2 tuples



## <a name="output--tu"></a>Saída : ('T],'U[])

Duas matrizes, a primeira contendo todos os primeiros elementos dos tuples de entrada, a segunda contendo todos os segundos elementos dos tuples de entrada.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo do primeiro elemento em cada tuple
### <a name="u"></a>'U

O tipo do segundo elemento em cada tuple

## <a name="example"></a>Exemplo

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)