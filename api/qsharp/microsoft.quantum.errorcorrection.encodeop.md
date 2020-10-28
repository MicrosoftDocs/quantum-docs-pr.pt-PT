---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Tipo definido pelo utilizador EncodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712347"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="36a2d-102">Tipo definido pelo utilizador EncodeOp</span><span class="sxs-lookup"><span data-stu-id="36a2d-102">EncodeOp user defined type</span></span>

<span data-ttu-id="36a2d-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="36a2d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="36a2d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36a2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36a2d-105">Representa uma operação que codifica um registo físico num registo lógico, utilizando os qubits de risco fornecidos.</span><span class="sxs-lookup"><span data-stu-id="36a2d-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="36a2d-106">O primeiro argumento é considerado o registo físico que será codificado, enquanto o segundo argumento é considerado como o registo de riscos que será utilizado.</span><span class="sxs-lookup"><span data-stu-id="36a2d-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

