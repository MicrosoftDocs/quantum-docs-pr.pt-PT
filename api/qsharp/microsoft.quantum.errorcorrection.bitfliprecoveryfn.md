---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: Função BitFlipRecoveryFn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712498"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="f9430-102">Função BitFlipRecoveryFn</span><span class="sxs-lookup"><span data-stu-id="f9430-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="f9430-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f9430-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f9430-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9430-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9430-105">Função para recuperação As operações de Pauli para a medição dada da síndrome por procura de tabela para o código de viragem ⟦3, 1, 1⟧ bit flip.</span><span class="sxs-lookup"><span data-stu-id="f9430-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="f9430-106">Saída : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="f9430-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="f9430-107">Função do tipo `RecoveryFn` que faz uma medição da síndrome e `Result[]` devolve as `Pauli[]` operações que corrigem o erro detetado.</span><span class="sxs-lookup"><span data-stu-id="f9430-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9430-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f9430-108">See Also</span></span>

- [<span data-ttu-id="f9430-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="f9430-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)