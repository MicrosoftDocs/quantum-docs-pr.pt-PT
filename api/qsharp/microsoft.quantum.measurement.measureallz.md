---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operação MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711073"
---
# <a name="measureallz-operation"></a><span data-ttu-id="941a1-102">Operação MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="941a1-102">MeasureAllZ operation</span></span>

<span data-ttu-id="941a1-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="941a1-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="941a1-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="941a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="941a1-105">Mede conjuntamente um registo de qubits na base Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="941a1-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="941a1-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="941a1-106">Description</span></span>

<span data-ttu-id="941a1-107">Mede um registo de qubits na base $Z \otimes Z \otimes \cdots \otimes Z$ base, representando a paridade de todo o registo.</span><span class="sxs-lookup"><span data-stu-id="941a1-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="941a1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="941a1-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="941a1-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="941a1-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="941a1-110">O registo a medir.</span><span class="sxs-lookup"><span data-stu-id="941a1-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="941a1-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="941a1-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="941a1-112">O resultado da medição $Z \otimes Z \otimes \cdots \otimes Z$.</span><span class="sxs-lookup"><span data-stu-id="941a1-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>