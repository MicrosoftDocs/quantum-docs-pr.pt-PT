---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Função LessThanOrEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709950"
---
# <a name="lessthanorequald-function"></a>Função LessThanOrEqualD

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


Retorna verdadeira se e somente se um número for inferior ou igual a outro número.

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--double"></a>a : [Duplo](xref:microsoft.quantum.lang-ref.double)

O primeiro valor a ser comparado.


### <a name="b--double"></a>b : [Duplo](xref:microsoft.quantum.lang-ref.double)

O segundo valor a ser comparado.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se `a` for inferior ou igual a `b` .

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```