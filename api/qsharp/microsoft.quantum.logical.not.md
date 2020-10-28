---
uid: Microsoft.Quantum.Logical.Not
title: Não funcionar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709866"
---
# <a name="not-function"></a>Não funcionar

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


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

```Q#
let x = not value;
let x = Not(value);
```