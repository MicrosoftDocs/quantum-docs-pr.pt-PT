---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: Função SteaneCodeRecoveryX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200375"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="cedb6-102">Função SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="cedb6-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="cedb6-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cedb6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cedb6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cedb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cedb6-105">Descodificador para a parte X do grupo estabilizador do código quântico ⟦ 1, 3⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="cedb6-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="cedb6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cedb6-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="cedb6-107">síndrome : [Síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="cedb6-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="cedb6-108">Uma matriz de síndrome obtida a partir da medição da parte X do estabilizador.</span><span class="sxs-lookup"><span data-stu-id="cedb6-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="cedb6-109">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cedb6-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="cedb6-110">Um conjunto de operações de Pauli que, quando aplicadas ao sistema quântico codificado, corrige o erro correspondente a `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="cedb6-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cedb6-111">Observações</span><span class="sxs-lookup"><span data-stu-id="cedb6-111">Remarks</span></span>

<span data-ttu-id="cedb6-112">O descodificador escolhido utiliza a propriedade de código CSS do código ⟦7, 1, 3⟧ código Steane, ou seja, corrige erros X e Z separadamente.</span><span class="sxs-lookup"><span data-stu-id="cedb6-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="cedb6-113">Uma propriedade do código é que a localização do X, respectivamente, a correção Z a aplicar é a codificação de 3 bits do X, respectivamente, síndrome de Z quando considerada um inteiro.</span><span class="sxs-lookup"><span data-stu-id="cedb6-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="cedb6-114">Referências</span><span class="sxs-lookup"><span data-stu-id="cedb6-114">References</span></span>

- <span data-ttu-id="cedb6-115">D.</span><span class="sxs-lookup"><span data-stu-id="cedb6-115">D.</span></span> <span data-ttu-id="cedb6-116">Gottesman, "Códigos estabilizadores e Correção de Erros Quânticos", Tese de Doutoramento, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="cedb6-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="cedb6-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cedb6-117">See Also</span></span>

- [<span data-ttu-id="cedb6-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="cedb6-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="cedb6-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="cedb6-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)