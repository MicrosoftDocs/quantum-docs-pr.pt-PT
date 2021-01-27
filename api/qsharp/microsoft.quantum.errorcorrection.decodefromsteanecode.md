---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Descodificar OperaçãoFromSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827395"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="27fb4-102">Descodificar OperaçãoFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="27fb4-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="27fb4-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="27fb4-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="27fb4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27fb4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27fb4-105">Uma operação de codificação inversa que mapeia um registo quântico não codificado para um registo quântico codificado sob o código quântico de ⟦7, 1, 3⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="27fb4-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="27fb4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="27fb4-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="27fb4-107">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="27fb4-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="27fb4-108">Uma série de qubits que representam o estado lógico codificado do código 5-qubit.</span><span class="sxs-lookup"><span data-stu-id="27fb4-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="27fb4-109">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="27fb4-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="27fb4-110">Uma matriz qubit de comprimento 1 representando o estado não codificado no primeiro parâmetro, juntamente com qubits auxiliares no segundo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="27fb4-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="27fb4-111">Observações</span><span class="sxs-lookup"><span data-stu-id="27fb4-111">Remarks</span></span>

<span data-ttu-id="27fb4-112">O descodificador escolhido utiliza a propriedade de código CSS do código ⟦7, 1, 3⟧ código Steane, ou seja, corrige erros X e Z separadamente.</span><span class="sxs-lookup"><span data-stu-id="27fb4-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="27fb4-113">Uma propriedade do código é que a localização do X, respectivamente, a correção Z a aplicar é a codificação de 3 bits do X, respectivamente, síndrome de Z quando considerada um inteiro.</span><span class="sxs-lookup"><span data-stu-id="27fb4-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="27fb4-114">Referências</span><span class="sxs-lookup"><span data-stu-id="27fb4-114">References</span></span>

- <span data-ttu-id="27fb4-115">D.</span><span class="sxs-lookup"><span data-stu-id="27fb4-115">D.</span></span> <span data-ttu-id="27fb4-116">Gottesman, "Códigos estabilizadores e Correção de Erros Quânticos", Tese de Doutoramento, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="27fb4-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="27fb4-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="27fb4-117">See Also</span></span>

- [<span data-ttu-id="27fb4-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="27fb4-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="27fb4-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="27fb4-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="27fb4-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="27fb4-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)