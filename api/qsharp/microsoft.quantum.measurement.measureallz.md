---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operação MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854678"
---
# <a name="measureallz-operation"></a><span data-ttu-id="2bbc8-102">Operação MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="2bbc8-102">MeasureAllZ operation</span></span>

<span data-ttu-id="2bbc8-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="2bbc8-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="2bbc8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bbc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bbc8-105">Mede conjuntamente um registo de qubits na base Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="2bbc8-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="2bbc8-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="2bbc8-106">Description</span></span>

<span data-ttu-id="2bbc8-107">Mede um registo de qubits na base $Z \otimes Z \otimes \cdots \otimes Z$ base, representando a paridade de todo o registo.</span><span class="sxs-lookup"><span data-stu-id="2bbc8-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="2bbc8-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2bbc8-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="2bbc8-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2bbc8-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2bbc8-110">O registo a medir.</span><span class="sxs-lookup"><span data-stu-id="2bbc8-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="2bbc8-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="2bbc8-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="2bbc8-112">O resultado da medição $Z \otimes Z \otimes \cdots \otimes Z$.</span><span class="sxs-lookup"><span data-stu-id="2bbc8-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>