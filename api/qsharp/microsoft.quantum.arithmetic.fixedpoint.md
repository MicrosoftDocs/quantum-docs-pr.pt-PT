---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definido pelo utilizador FixedPoint
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223107"
---
# <a name="fixedpoint-user-defined-type"></a>Tipo definido pelo utilizador FixedPoint

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Representa um registo de qubits codificando um número de ponto fixo. Consiste num número inteiro que é igual ao número de qubits à esquerda do ponto binário, ou seja, qubits de peso superior ou igual a 1, e um registo quântico.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

