---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operação de Medida de Assert
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853507"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="da9d2-102">Operação de Medida de Assert</span><span class="sxs-lookup"><span data-stu-id="da9d2-102">AssertMeasurement operation</span></span>

<span data-ttu-id="da9d2-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="da9d2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="da9d2-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="da9d2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="da9d2-105">Afirma que medir os qubits dado na dada base Pauli terá sempre o resultado dado.</span><span class="sxs-lookup"><span data-stu-id="da9d2-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="da9d2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="da9d2-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="da9d2-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="da9d2-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="da9d2-108">Um efeito de medição para afirmar a probabilidade de, expressa como um operador pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="da9d2-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="da9d2-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="da9d2-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="da9d2-110">Um registo para fazer a afirmação.</span><span class="sxs-lookup"><span data-stu-id="da9d2-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="da9d2-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="da9d2-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="da9d2-112">O resultado esperado de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="da9d2-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="da9d2-113">msg : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="da9d2-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="da9d2-114">Uma mensagem a ser reportada se a afirmação falhar.</span><span class="sxs-lookup"><span data-stu-id="da9d2-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da9d2-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da9d2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da9d2-116">Observações</span><span class="sxs-lookup"><span data-stu-id="da9d2-116">Remarks</span></span>

<span data-ttu-id="da9d2-117">Note que as versões adjacentes e controladas desta operação não verificarão a condição.</span><span class="sxs-lookup"><span data-stu-id="da9d2-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="da9d2-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="da9d2-118">See Also</span></span>

- [<span data-ttu-id="da9d2-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="da9d2-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)