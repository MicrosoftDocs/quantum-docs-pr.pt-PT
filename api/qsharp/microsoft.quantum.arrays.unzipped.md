---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Função desapertado
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718787"
---
# <a name="unzipped-function"></a>Função desapertado

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Zipped](xref:Microsoft.Quantum.Arrays.Zipped)