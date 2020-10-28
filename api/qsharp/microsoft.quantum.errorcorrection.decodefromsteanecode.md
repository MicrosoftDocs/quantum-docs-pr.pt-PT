---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Descodificar OperaçãoFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712417"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="d8b74-102">Descodificar OperaçãoFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="d8b74-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="d8b74-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d8b74-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d8b74-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8b74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8b74-105">Uma operação de codificação inversa que mapeia um registo quântico não codificado para um registo quântico codificado sob o código quântico de ⟦7, 1, 3⟧ Steane.</span><span class="sxs-lookup"><span data-stu-id="d8b74-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="d8b74-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d8b74-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="d8b74-107">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="d8b74-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="d8b74-108">Uma série de qubits que representam o estado lógico codificado do código 5-qubit.</span><span class="sxs-lookup"><span data-stu-id="d8b74-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="d8b74-109">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="d8b74-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="d8b74-110">Uma matriz qubit de comprimento 1 representando o estado não codificado no primeiro parâmetro, juntamente com qubits auxiliares no segundo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d8b74-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8b74-111">Observações</span><span class="sxs-lookup"><span data-stu-id="d8b74-111">Remarks</span></span>

<span data-ttu-id="d8b74-112">O descodificador escolhido utiliza a propriedade de código CSS do código ⟦7, 1, 3⟧ código Steane, ou seja, corrige erros X e Z separadamente.</span><span class="sxs-lookup"><span data-stu-id="d8b74-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="d8b74-113">Uma propriedade do código é que a localização do X, respectivamente, a correção Z a aplicar é a codificação de 3 bits do X, respectivamente, síndrome de Z quando considerada um inteiro.</span><span class="sxs-lookup"><span data-stu-id="d8b74-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="d8b74-114">Referências</span><span class="sxs-lookup"><span data-stu-id="d8b74-114">References</span></span>

- <span data-ttu-id="d8b74-115">D.</span><span class="sxs-lookup"><span data-stu-id="d8b74-115">D.</span></span> <span data-ttu-id="d8b74-116">Gottesman, "Códigos estabilizadores e Correção de Erros Quânticos", Tese de Doutoramento, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="d8b74-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="d8b74-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d8b74-117">See Also</span></span>

- [<span data-ttu-id="d8b74-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="d8b74-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="d8b74-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="d8b74-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="d8b74-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="d8b74-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)