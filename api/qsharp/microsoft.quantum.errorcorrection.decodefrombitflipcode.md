---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Descodificar operaçãoFromBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b16e84340053b6c1eab7b91ed8db0461b9eac98e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827569"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="a1b72-102">Descodificar operaçãoFromBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="a1b72-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="a1b72-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a1b72-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a1b72-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1b72-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1b72-105">Descodifica do código bit-flip [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip.</span><span class="sxs-lookup"><span data-stu-id="a1b72-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="a1b72-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a1b72-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="a1b72-107">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="a1b72-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="a1b72-108">Um bloco de código do código bit-flip.</span><span class="sxs-lookup"><span data-stu-id="a1b72-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="a1b72-109">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="a1b72-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="a1b72-110">Um tuple dos dados codificados no registo lógico, e os qubits auxiliares usados para representar a síndrome.</span><span class="sxs-lookup"><span data-stu-id="a1b72-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1b72-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a1b72-111">See Also</span></span>

- [<span data-ttu-id="a1b72-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="a1b72-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="a1b72-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="a1b72-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)