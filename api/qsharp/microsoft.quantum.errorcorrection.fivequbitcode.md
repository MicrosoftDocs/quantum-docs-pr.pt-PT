---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Função FiveQubitCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200888"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="45855-102">Função FiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="45855-102">FiveQubitCode function</span></span>

<span data-ttu-id="45855-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="45855-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="45855-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45855-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45855-105">Devolve um valor QECC que representa o codificador de código ⟦5, 1, 3⟧ com a medição da síndrome no local.</span><span class="sxs-lookup"><span data-stu-id="45855-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="45855-106">Saída : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="45855-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="45855-107">Devolve uma implementação de um código de correção de erros quânticos especificando um `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="45855-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="45855-108">Observações</span><span class="sxs-lookup"><span data-stu-id="45855-108">Remarks</span></span>

<span data-ttu-id="45855-109">Este código foi encontrado independentemente nos dois seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="45855-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="45855-110">C.</span><span class="sxs-lookup"><span data-stu-id="45855-110">C.</span></span> <span data-ttu-id="45855-111">H.</span><span class="sxs-lookup"><span data-stu-id="45855-111">H.</span></span> <span data-ttu-id="45855-112">Bennett, D. DiVincenzo, J.A.</span><span class="sxs-lookup"><span data-stu-id="45855-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="45855-113">Smolin e W.K.</span><span class="sxs-lookup"><span data-stu-id="45855-113">Smolin and W. K.</span></span> <span data-ttu-id="45855-114">Wootters, "Emaranhado de estado misto e correção de erros quânticos", Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 e</span><span class="sxs-lookup"><span data-stu-id="45855-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="45855-115">R.</span><span class="sxs-lookup"><span data-stu-id="45855-115">R.</span></span> <span data-ttu-id="45855-116">Laflamme, C. Miquel, J.P.</span><span class="sxs-lookup"><span data-stu-id="45855-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="45855-117">Paz e W. H.</span><span class="sxs-lookup"><span data-stu-id="45855-117">Paz and W. H.</span></span> <span data-ttu-id="45855-118">Zurek, "Código perfeito de correção de erros quânticos", Phys. Rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="45855-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="45855-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="45855-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>