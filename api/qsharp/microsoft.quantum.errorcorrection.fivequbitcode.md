---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Função FiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853143"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="17852-102">Função FiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="17852-102">FiveQubitCode function</span></span>

<span data-ttu-id="17852-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="17852-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="17852-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17852-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17852-105">Devolve um valor QECC que representa o codificador de código ⟦5, 1, 3⟧ com a medição da síndrome no local.</span><span class="sxs-lookup"><span data-stu-id="17852-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="17852-106">Saída : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="17852-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="17852-107">Devolve uma implementação de um código de correção de erros quânticos especificando um `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="17852-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="17852-108">Observações</span><span class="sxs-lookup"><span data-stu-id="17852-108">Remarks</span></span>

<span data-ttu-id="17852-109">Este código foi encontrado independentemente nos dois seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="17852-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="17852-110">C.</span><span class="sxs-lookup"><span data-stu-id="17852-110">C.</span></span> <span data-ttu-id="17852-111">H.</span><span class="sxs-lookup"><span data-stu-id="17852-111">H.</span></span> <span data-ttu-id="17852-112">Bennett, D. DiVincenzo, J.A.</span><span class="sxs-lookup"><span data-stu-id="17852-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="17852-113">Smolin e W.K.</span><span class="sxs-lookup"><span data-stu-id="17852-113">Smolin and W. K.</span></span> <span data-ttu-id="17852-114">Wootters, "Emaranhado de estado misto e correção de erros quânticos", Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 e</span><span class="sxs-lookup"><span data-stu-id="17852-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="17852-115">R.</span><span class="sxs-lookup"><span data-stu-id="17852-115">R.</span></span> <span data-ttu-id="17852-116">Laflamme, C. Miquel, J.P.</span><span class="sxs-lookup"><span data-stu-id="17852-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="17852-117">Paz e W. H.</span><span class="sxs-lookup"><span data-stu-id="17852-117">Paz and W. H.</span></span> <span data-ttu-id="17852-118">Zurek, "Código perfeito de correção de erros quânticos", Phys. Rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="17852-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="17852-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="17852-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>