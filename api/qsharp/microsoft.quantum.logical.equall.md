---
uid: Microsoft.Quantum.Logical.EqualL
title: Função EqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710037"
---
# <a name="equall-function"></a>Função EqualL

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [](https://nuget.org/packages/)


Retorna verdadeira se e somente se duas entradas forem iguais.

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O primeiro valor a ser comparado.


### <a name="b--bigint"></a>b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O segundo valor a ser comparado.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se `a` for igual a `b` .

## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```