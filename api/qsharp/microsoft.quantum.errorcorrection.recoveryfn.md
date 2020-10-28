---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: RecoveryFn tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712193"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="d9135-102">RecoveryFn tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="d9135-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="d9135-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d9135-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d9135-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9135-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9135-105">Digite para a função que mapeia uma síndrome de erro para uma sequência de `Pauli[]` operações que corrigem o erro detetado.</span><span class="sxs-lookup"><span data-stu-id="d9135-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

