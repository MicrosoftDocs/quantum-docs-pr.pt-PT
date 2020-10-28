---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Função NotEqualR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709796"
---
# <a name="notequalr-function"></a>Função NotEqualR

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


Retorna verdadeira se e somente se duas entradas não forem iguais.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--__invalidresult__"></a>a : __inválido <Result>__

O primeiro valor a ser comparado.


### <a name="b--__invalidresult__"></a>b : __inválido <Result>__

O segundo valor a ser comparado.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente `a` se não for igual a `b` .

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```