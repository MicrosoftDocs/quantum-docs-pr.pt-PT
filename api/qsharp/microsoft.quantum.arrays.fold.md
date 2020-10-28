---
uid: Microsoft.Quantum.Arrays.Fold
title: Função dobrável
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719207"
---
# <a name="fold-function"></a>Função dobrável

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Iterates uma função `f` através de uma `array` matriz, retornando `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Entrada

### <a name="folder--statet---state"></a>pasta : ('Estado,'T) -> 'Estado

Uma função a ser dobrada sobre a matriz.


### <a name="state--state"></a>estado : 'Estado

O estado inicial da pasta.


### <a name="array--t"></a>matriz : 'T[]

Uma variedade de valores a dobrar.



## <a name="output--state"></a>Saída : 'Estado

O estado final devolvido pela pasta depois de iterar sobre todos os elementos de `array` .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="state"></a>'Estado

O tipo de estados em que a `folder` função funciona, ou seja, aceita como primeiro argumento e regressa.
### <a name="t"></a>'T

O tipo de `array` elementos.