---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: Função SteaneCodeRecoveryX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712134"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="a52dc-102">Função SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="a52dc-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="a52dc-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a52dc-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a52dc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a52dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a52dc-105">Descodificador para a parte X do grupo estabilizador do código quântico ⟦ 1, 3⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="a52dc-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="a52dc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a52dc-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="a52dc-107">síndrome : [Síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="a52dc-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="a52dc-108">Uma matriz de síndrome obtida a partir da medição da parte X do estabilizador.</span><span class="sxs-lookup"><span data-stu-id="a52dc-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="a52dc-109">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a52dc-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a52dc-110">Um conjunto de operações de Pauli que, quando aplicadas ao sistema quântico codificado, corrige o erro correspondente a `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="a52dc-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a52dc-111">Observações</span><span class="sxs-lookup"><span data-stu-id="a52dc-111">Remarks</span></span>

<span data-ttu-id="a52dc-112">O descodificador escolhido utiliza a propriedade de código CSS do código ⟦7, 1, 3⟧ código Steane, ou seja, corrige erros X e Z separadamente.</span><span class="sxs-lookup"><span data-stu-id="a52dc-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="a52dc-113">Uma propriedade do código é que a localização do X, respectivamente, a correção Z a aplicar é a codificação de 3 bits do X, respectivamente, síndrome de Z quando considerada um inteiro.</span><span class="sxs-lookup"><span data-stu-id="a52dc-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="a52dc-114">Referências</span><span class="sxs-lookup"><span data-stu-id="a52dc-114">References</span></span>

- <span data-ttu-id="a52dc-115">D.</span><span class="sxs-lookup"><span data-stu-id="a52dc-115">D.</span></span> <span data-ttu-id="a52dc-116">Gottesman, "Códigos estabilizadores e Correção de Erros Quânticos", Tese de Doutoramento, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="a52dc-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="a52dc-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a52dc-117">See Also</span></span>

- [<span data-ttu-id="a52dc-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="a52dc-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="a52dc-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="a52dc-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)