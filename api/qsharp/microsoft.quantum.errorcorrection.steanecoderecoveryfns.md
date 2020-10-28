---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: Função SteaneCodeRecoveryFns
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712137"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="fbc46-102">Função SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="fbc46-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="fbc46-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="fbc46-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="fbc46-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbc46-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbc46-105">Descodificador para partes combinadas de X e Z do grupo estabilizador do código quântico ⟦ 1, 1, 3⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="fbc46-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="fbc46-106">Saída :[(RecoveryFn,](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)[RecoveryFn)](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="fbc46-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="fbc46-107">Tuple de funções do tipo `RecoveryFn` que faz uma medição de síndrome e `Result[]` devolve as `Pauli[]` operações que corrigem o erro detetado.</span><span class="sxs-lookup"><span data-stu-id="fbc46-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbc46-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fbc46-108">See Also</span></span>

- [<span data-ttu-id="fbc46-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="fbc46-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="fbc46-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span><span class="sxs-lookup"><span data-stu-id="fbc46-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)