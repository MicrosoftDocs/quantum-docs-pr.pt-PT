---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operação afirmaMeasurementProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202367"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="cd85f-102">Operação afirmaMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="cd85f-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="cd85f-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cd85f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cd85f-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cd85f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cd85f-105">Afirma que medir os qubits dado na dada base Pauli terá o resultado dado com a dada probabilidade, dentro de alguma tolerância.</span><span class="sxs-lookup"><span data-stu-id="cd85f-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cd85f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cd85f-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="cd85f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cd85f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="cd85f-108">Um efeito de medição para afirmar a probabilidade de, expressa como um operador pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="cd85f-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cd85f-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd85f-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd85f-110">Um registo para fazer a afirmação.</span><span class="sxs-lookup"><span data-stu-id="cd85f-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="cd85f-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="cd85f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="cd85f-112">Um resultado esperado `Measure(bases, qubits)` de.</span><span class="sxs-lookup"><span data-stu-id="cd85f-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="cd85f-113">prob : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd85f-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd85f-114">A probabilidade com que o resultado é esperado.</span><span class="sxs-lookup"><span data-stu-id="cd85f-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="cd85f-115">msg : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cd85f-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cd85f-116">Uma mensagem a ser reportada se a afirmação falhar.</span><span class="sxs-lookup"><span data-stu-id="cd85f-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="cd85f-117">tol : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd85f-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="cd85f-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd85f-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cd85f-119">Observações</span><span class="sxs-lookup"><span data-stu-id="cd85f-119">Remarks</span></span>

<span data-ttu-id="cd85f-120">Note que as versões adjacentes e controladas desta operação não verificarão a condição.</span><span class="sxs-lookup"><span data-stu-id="cd85f-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd85f-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cd85f-121">See Also</span></span>

- [<span data-ttu-id="cd85f-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span><span class="sxs-lookup"><span data-stu-id="cd85f-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)