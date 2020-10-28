---
uid: Microsoft.Quantum.ErrorCorrection.QECC
title: Tipo definido pelo utilizador QECC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: QECC
qsharp.summary: Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.
ms.openlocfilehash: 6a00875f53928da4e0b8da6a3e32e37a551a56b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712249"
---
# <a name="qecc-user-defined-type"></a><span data-ttu-id="4f0e6-102">Tipo definido pelo utilizador QECC</span><span class="sxs-lookup"><span data-stu-id="4f0e6-102">QECC user defined type</span></span>

<span data-ttu-id="4f0e6-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4f0e6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4f0e6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f0e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f0e6-105">Representa um código de correção de erros, tal como definido pelo seu procedimento de medição do codificador, descodificador e síndrome.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-105">Represents an error-correcting code as defined by its encoder, decoder, and syndrome measurement procedure.</span></span>

```qsharp

newtype QECC = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

