---
uid: Microsoft.Quantum.Logical.Not
title: Não funcionar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197454"
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

```Q#
let x = not value;
let x = Not(value);
```