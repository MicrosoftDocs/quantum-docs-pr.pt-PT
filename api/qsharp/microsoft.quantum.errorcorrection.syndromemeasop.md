---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido pelo utilizador SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712120"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="ec1d1-102">Tipo definido pelo utilizador SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="ec1d1-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="ec1d1-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ec1d1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ec1d1-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec1d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec1d1-105">Representa uma operação que é usada para medir a síndrome de um bloco de código que corrige erros.</span><span class="sxs-lookup"><span data-stu-id="ec1d1-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="ec1d1-106">Observações</span><span class="sxs-lookup"><span data-stu-id="ec1d1-106">Remarks</span></span>

<span data-ttu-id="ec1d1-107">A assinatura `(LogicalRegister => Syndrome)` representa uma operação que atua conjuntamente nos qubits `LogicalRegister` e alguns qubits auxiliares seguidos de uma medição dos qubits auxiliares para extrair um `Syndrome` valor que representa as `Result[]` destas medições.</span><span class="sxs-lookup"><span data-stu-id="ec1d1-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec1d1-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ec1d1-108">See Also</span></span>

- [<span data-ttu-id="ec1d1-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ec1d1-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="ec1d1-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span><span class="sxs-lookup"><span data-stu-id="ec1d1-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)