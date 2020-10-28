---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Descodificar operaçãoFromBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712484"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="79585-102">Descodificar operaçãoFromBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="79585-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="79585-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="79585-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="79585-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79585-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79585-105">Descodifica do código bit-flip [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip.</span><span class="sxs-lookup"><span data-stu-id="79585-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="79585-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="79585-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="79585-107">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="79585-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="79585-108">Um bloco de código do código bit-flip.</span><span class="sxs-lookup"><span data-stu-id="79585-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="79585-109">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="79585-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="79585-110">Um tuple dos dados codificados no registo lógico, e os qubits auxiliares usados para representar a síndrome.</span><span class="sxs-lookup"><span data-stu-id="79585-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="79585-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="79585-111">See Also</span></span>

- [<span data-ttu-id="79585-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="79585-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="79585-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="79585-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)