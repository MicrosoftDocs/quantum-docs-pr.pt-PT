---
uid: Microsoft.Quantum.ErrorCorrection.CSS
title: Tipo definido pelo utilizador CSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: CSS
qsharp.summary: Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.
ms.openlocfilehash: c5227c771ec2c7c81d05a28681745af641eebeaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712487"
---
# <a name="css-user-defined-type"></a><span data-ttu-id="ac1ba-102">Tipo definido pelo utilizador CSS</span><span class="sxs-lookup"><span data-stu-id="ac1ba-102">CSS user defined type</span></span>

<span data-ttu-id="ac1ba-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ac1ba-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ac1ba-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac1ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac1ba-105">Representa um código Calderbank-Shor-Steane (CSS) definido pelo seu codificador, descodificador e seus procedimentos de medição de síndrome para `X` e `Z` erros, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ac1ba-105">Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.</span></span>

```qsharp

newtype CSS = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

