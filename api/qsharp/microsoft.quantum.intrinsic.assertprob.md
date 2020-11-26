---
uid: Microsoft.Quantum.Intrinsic.AssertProb
title: Operação AssertProb
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: AssertProb
qsharp.summary: >-
  > [!WARNING]

  > AssertProb has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.
ms.openlocfilehash: 3c0f7c7a9e0190c5a8e5f3e70a5f82a8c23a97bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199102"
---
# <a name="assertprob-operation"></a><span data-ttu-id="94b0e-102">Operação AssertProb</span><span class="sxs-lookup"><span data-stu-id="94b0e-102">AssertProb operation</span></span>

<span data-ttu-id="94b0e-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="94b0e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="94b0e-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="94b0e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="94b0e-105">A AssertProb foi depreocada.</span><span class="sxs-lookup"><span data-stu-id="94b0e-105">AssertProb has been deprecated.</span></span> <span data-ttu-id="94b0e-106">Por favor, use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="94b0e-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.</span></span>



```qsharp
operation AssertProb (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="94b0e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="94b0e-107">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="94b0e-108">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="94b0e-108">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="94b0e-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94b0e-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="result--__invalidresult__"></a><span data-ttu-id="94b0e-110">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="94b0e-110">result : __invalid<Result>__</span></span>




### <a name="prob--double"></a><span data-ttu-id="94b0e-111">prob : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94b0e-111">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="msg--string"></a><span data-ttu-id="94b0e-112">msg : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="94b0e-112">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>




### <a name="tol--double"></a><span data-ttu-id="94b0e-113">tol : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94b0e-113">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="94b0e-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94b0e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

