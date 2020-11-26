---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido pelo utilizador SyndromeMeasOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200259"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="ebfef-102">Tipo definido pelo utilizador SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="ebfef-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="ebfef-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ebfef-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ebfef-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebfef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebfef-105">Representa uma operação que é usada para medir a síndrome de um bloco de código que corrige erros.</span><span class="sxs-lookup"><span data-stu-id="ebfef-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="ebfef-106">Observações</span><span class="sxs-lookup"><span data-stu-id="ebfef-106">Remarks</span></span>

<span data-ttu-id="ebfef-107">A assinatura `(LogicalRegister => Syndrome)` representa uma operação que atua conjuntamente nos qubits `LogicalRegister` e alguns qubits auxiliares seguidos de uma medição dos qubits auxiliares para extrair um `Syndrome` valor que representa as `Result[]` destas medições.</span><span class="sxs-lookup"><span data-stu-id="ebfef-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebfef-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ebfef-108">See Also</span></span>

- [<span data-ttu-id="ebfef-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ebfef-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="ebfef-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span><span class="sxs-lookup"><span data-stu-id="ebfef-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)