---
uid: Microsoft.Quantum.Logical.Not
title: Não funcionar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849079"
---
# <a name="not-function"></a>Não funcionar

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a negação booleana de um valor.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="value--bool"></a>valor : [Bool](xref:microsoft.quantum.lang-ref.bool)

O valor a ser negado.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se `value` for `false` .

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```qsharp
let x = not value;
let x = Not(value);
```