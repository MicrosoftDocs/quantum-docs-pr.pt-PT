---
uid: Microsoft.Quantum.Logical.And
title: E funcionar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849234"
---
# <a name="and-function"></a>E funcionar

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = a and b;
let x = And(a, b);
```