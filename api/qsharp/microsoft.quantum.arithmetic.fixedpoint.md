---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definido pelo utilizador FixedPoint
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843195"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="f6d0e-102">Tipo definido pelo utilizador FixedPoint</span><span class="sxs-lookup"><span data-stu-id="f6d0e-102">FixedPoint user defined type</span></span>

<span data-ttu-id="f6d0e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f6d0e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f6d0e-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f6d0e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f6d0e-105">Representa um registo de qubits codificando um número de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="f6d0e-106">Consiste num número inteiro que é igual ao número de qubits à esquerda do ponto binário, ou seja, qubits de peso superior ou igual a 1, e um registo quântico.</span><span class="sxs-lookup"><span data-stu-id="f6d0e-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

