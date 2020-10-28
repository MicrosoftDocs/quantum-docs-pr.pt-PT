---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: Função LessOrEqualI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: dd934fde3fae9c1a43032b4b08ac03afa72798d1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709936"
---
# <a name="lessthanorequali-function"></a>Função LessOrEqualI

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


Retorna verdadeira se e somente se um número for inferior ou igual a outro número.

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a : [Int](xref:microsoft.quantum.lang-ref.int)

O primeiro valor a ser comparado.


### <a name="b--int"></a>b : [Int](xref:microsoft.quantum.lang-ref.int)

O segundo valor a ser comparado.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se `a` for inferior ou igual a `b` .

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```