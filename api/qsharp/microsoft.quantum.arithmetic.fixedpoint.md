---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definido pelo utilizador FixedPoint
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721150"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="b8c83-102">Tipo definido pelo utilizador FixedPoint</span><span class="sxs-lookup"><span data-stu-id="b8c83-102">FixedPoint user defined type</span></span>

<span data-ttu-id="b8c83-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b8c83-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b8c83-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8c83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8c83-105">Representa um registo de qubits codificando um número de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="b8c83-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="b8c83-106">Consiste num número inteiro que é igual ao número de qubits à esquerda do ponto binário, ou seja, qubits de peso superior ou igual a 1, e um registo quântico.</span><span class="sxs-lookup"><span data-stu-id="b8c83-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

