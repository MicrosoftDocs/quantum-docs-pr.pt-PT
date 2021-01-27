---
uid: Microsoft.Quantum.Arrays.Fold
title: Função dobrável
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848611"
---
# <a name="fold-function"></a>Função dobrável

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemplo

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```