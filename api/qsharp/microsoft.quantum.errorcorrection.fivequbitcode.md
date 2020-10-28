---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Função FiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712344"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="14480-102">Função FiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="14480-102">FiveQubitCode function</span></span>

<span data-ttu-id="14480-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="14480-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="14480-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="14480-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="14480-105">Devolve um valor QECC que representa o codificador de código ⟦5, 1, 3⟧ com a medição da síndrome no local.</span><span class="sxs-lookup"><span data-stu-id="14480-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="14480-106">Saída : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="14480-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="14480-107">Devolve uma implementação de um código de correção de erros quânticos especificando um `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="14480-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="14480-108">Observações</span><span class="sxs-lookup"><span data-stu-id="14480-108">Remarks</span></span>

<span data-ttu-id="14480-109">Este código foi encontrado independentemente nos dois seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="14480-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="14480-110">C.</span><span class="sxs-lookup"><span data-stu-id="14480-110">C.</span></span> <span data-ttu-id="14480-111">H.</span><span class="sxs-lookup"><span data-stu-id="14480-111">H.</span></span> <span data-ttu-id="14480-112">Bennett, D. DiVincenzo, J.A.</span><span class="sxs-lookup"><span data-stu-id="14480-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="14480-113">Smolin e W.K.</span><span class="sxs-lookup"><span data-stu-id="14480-113">Smolin and W. K.</span></span> <span data-ttu-id="14480-114">Wootters, "Emaranhado de estado misto e correção de erros quânticos", Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 e</span><span class="sxs-lookup"><span data-stu-id="14480-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="14480-115">R.</span><span class="sxs-lookup"><span data-stu-id="14480-115">R.</span></span> <span data-ttu-id="14480-116">Laflamme, C. Miquel, J.P.</span><span class="sxs-lookup"><span data-stu-id="14480-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="14480-117">Paz e W. H.</span><span class="sxs-lookup"><span data-stu-id="14480-117">Paz and W. H.</span></span> <span data-ttu-id="14480-118">Zurek, "Código perfeito de correção de erros quânticos", Phys. Rev. Lett.</span><span class="sxs-lookup"><span data-stu-id="14480-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="14480-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="14480-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>