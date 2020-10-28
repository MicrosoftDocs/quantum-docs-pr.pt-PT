---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operação EncodeIntoBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712403"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="71ad7-102">Operação EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="71ad7-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="71ad7-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="71ad7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="71ad7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71ad7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71ad7-105">Codifica o código bit-flip [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip.</span><span class="sxs-lookup"><span data-stu-id="71ad7-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="71ad7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="71ad7-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="71ad7-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71ad7-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71ad7-108">Um registo de qubits físicos que representam os dados a proteger.</span><span class="sxs-lookup"><span data-stu-id="71ad7-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="71ad7-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71ad7-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71ad7-110">Um registo de qubits auxiliares inicialmente no estado $\ket {00} $ a ser usado na codificação dos dados a proteger.</span><span class="sxs-lookup"><span data-stu-id="71ad7-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="71ad7-111">Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="71ad7-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="71ad7-112">Os qubits físicos e auxiliares utilizados na codificação, representados como um registo lógico.</span><span class="sxs-lookup"><span data-stu-id="71ad7-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="71ad7-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="71ad7-113">See Also</span></span>

- [<span data-ttu-id="71ad7-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="71ad7-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)