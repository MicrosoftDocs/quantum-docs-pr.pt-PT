---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: Função SteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853060"
---
# <a name="steanecode-function"></a><span data-ttu-id="7bfd1-102">Função SteaneCode</span><span class="sxs-lookup"><span data-stu-id="7bfd1-102">SteaneCode function</span></span>

<span data-ttu-id="7bfd1-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7bfd1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7bfd1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bfd1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bfd1-105">Devolve um valor CSS que representa o codificador de código Steane ⟦7, 1, 3⟧ com a medição da síndrome in-place.</span><span class="sxs-lookup"><span data-stu-id="7bfd1-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="7bfd1-106">Saída : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="7bfd1-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="7bfd1-107">Um objeto do tipo CSS que recolhe todos os dados relevantes para executar a codificação e correção de erros para o código Steane ⟦7, 1, 3⟧.</span><span class="sxs-lookup"><span data-stu-id="7bfd1-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7bfd1-108">Observações</span><span class="sxs-lookup"><span data-stu-id="7bfd1-108">Remarks</span></span>

<span data-ttu-id="7bfd1-109">Este código foi encontrado no seguinte papel:</span><span class="sxs-lookup"><span data-stu-id="7bfd1-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="7bfd1-110">A.</span><span class="sxs-lookup"><span data-stu-id="7bfd1-110">A.</span></span> <span data-ttu-id="7bfd1-111">Steane, "Múltipla interferência de partículas e correção de erros quânticos", Proc.</span><span class="sxs-lookup"><span data-stu-id="7bfd1-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="7bfd1-112">Roy, o que estás a fazer</span><span class="sxs-lookup"><span data-stu-id="7bfd1-112">Roy.</span></span> <span data-ttu-id="7bfd1-113">Soc. Lond.</span><span class="sxs-lookup"><span data-stu-id="7bfd1-113">Soc. Lond.</span></span> <span data-ttu-id="7bfd1-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="7bfd1-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>