---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operação de reset
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198678"
---
# <a name="reset-operation"></a>Operação de reset

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Perante um único qubit, mede-o e garante que está no estado de [0⟩ de modo a poder ser libertado com segurança.

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit cujo estado deve ser reposto para $\ket {0} $.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

