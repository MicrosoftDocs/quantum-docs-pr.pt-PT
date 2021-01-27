---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operação EncodeIntoBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826685"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="e4b30-102">Operação EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="e4b30-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="e4b30-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e4b30-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e4b30-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4b30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4b30-105">Codifica o código bit-flip [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip.</span><span class="sxs-lookup"><span data-stu-id="e4b30-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="e4b30-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e4b30-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="e4b30-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4b30-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4b30-108">Um registo de qubits físicos que representam os dados a proteger.</span><span class="sxs-lookup"><span data-stu-id="e4b30-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="e4b30-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4b30-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e4b30-110">Um registo de qubits auxiliares inicialmente no estado $\ket {00} $ a ser usado na codificação dos dados a proteger.</span><span class="sxs-lookup"><span data-stu-id="e4b30-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="e4b30-111">Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e4b30-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e4b30-112">Os qubits físicos e auxiliares utilizados na codificação, representados como um registo lógico.</span><span class="sxs-lookup"><span data-stu-id="e4b30-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4b30-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e4b30-113">See Also</span></span>

- [<span data-ttu-id="e4b30-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e4b30-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)