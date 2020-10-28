---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Função CumulativeFolded
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719398"
---
# <a name="cumulativefolded-function"></a>Função CumulativeFolded

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Combina Mapeado e Dobre numa única função

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Descrição

Esta função iteriza a `fn` função através da matriz, partindo de um estado inicial `state` e devolve todos os valores intermédios, sem incluir o estado inicial.

## <a name="input"></a>Entrada

### <a name="fn--statet---state"></a>fn : ('Estado,'T) -> 'Estado

Uma função a ser dobrada sobre a matriz


### <a name="state--state"></a>estado : 'Estado

O estado inicial a ser dobrado


### <a name="array--t"></a>matriz : 'T[]

Uma matriz de valores a dobrar



## <a name="output--state"></a>Saída : 'Estado].

Todos os estados intermédios, incluindo o estado final, mas não o estado inicial.
O comprimento da matriz de saída tem o mesmo comprimento que `array` . .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="state"></a>'Estado

O tipo de estados em que a `fn` função funciona, ou seja, aceita como primeira entrada e retorno.
### <a name="t"></a>'T

O tipo de `array` elementos.