---
uid: Microsoft.Quantum.Logical.Or
title: Ou função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719975"
---
# <a name="or-function"></a>Ou função

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


Devolve a disjunção booleana de dois valores.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>a : [Bool](xref:microsoft.quantum.lang-ref.bool)

O primeiro valor a ser considerado.


### <a name="b--bool"></a>b : [Bool](xref:microsoft.quantum.lang-ref.bool)

O segundo valor a considerar.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se `a` um ou o são `b` `true` .

## <a name="remarks"></a>Observações

Ao contrário do `or` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.

Até um comportamento de curto-circuito, os seguintes são equivalentes:

```Q#
let x = a or b;
let x = Or(a, b);
```