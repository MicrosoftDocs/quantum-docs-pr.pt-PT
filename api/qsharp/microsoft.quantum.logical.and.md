---
uid: Microsoft.Quantum.Logical.And
title: E funcionar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720802"
---
# <a name="and-function"></a>E funcionar

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


Devolve a conjunção Booleana de dois valores.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>a : [Bool](xref:microsoft.quantum.lang-ref.bool)

O primeiro valor a ser considerado.


### <a name="b--bool"></a>b : [Bool](xref:microsoft.quantum.lang-ref.bool)

O segundo valor a considerar.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se `a` e `b` são ambos `true` .

## <a name="remarks"></a>Observações

Ao contrário do `and` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.

Até um comportamento de curto-circuito, os seguintes são equivalentes:

```Q#
let x = a and b;
let x = And(a, b);
```