---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operação MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227085"
---
# <a name="measureallz-operation"></a><span data-ttu-id="d5a0d-102">Operação MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="d5a0d-102">MeasureAllZ operation</span></span>

<span data-ttu-id="d5a0d-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d5a0d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d5a0d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5a0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5a0d-105">Mede conjuntamente um registo de qubits na base Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="d5a0d-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="d5a0d-106">Description</span><span class="sxs-lookup"><span data-stu-id="d5a0d-106">Description</span></span>

<span data-ttu-id="d5a0d-107">Mede um registo de qubits na base $Z \otimes Z \otimes \cdots \otimes Z$ base, representando a paridade de todo o registo.</span><span class="sxs-lookup"><span data-stu-id="d5a0d-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="d5a0d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d5a0d-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="d5a0d-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5a0d-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5a0d-110">O registo a medir.</span><span class="sxs-lookup"><span data-stu-id="d5a0d-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d5a0d-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="d5a0d-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d5a0d-112">O resultado da medição $Z \otimes Z \otimes \cdots \otimes Z$.</span><span class="sxs-lookup"><span data-stu-id="d5a0d-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>