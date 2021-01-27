---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Tipo definido pelo utilizador EncodeOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: c9959f1afbd44df974c06b79f73eccd090b17985
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826182"
---
# <a name="encodeop-user-defined-type"></a>Tipo definido pelo utilizador EncodeOp

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma operação que codifica um registo físico num registo lógico, utilizando os qubits de risco fornecidos.

O primeiro argumento é considerado o registo físico que será codificado, enquanto o segundo argumento é considerado como o registo de riscos que será utilizado.

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

