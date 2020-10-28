---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operação de Medida de Assert
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713033"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="b6f89-102">Operação de Medida de Assert</span><span class="sxs-lookup"><span data-stu-id="b6f89-102">AssertMeasurement operation</span></span>

<span data-ttu-id="b6f89-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b6f89-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b6f89-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6f89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6f89-105">Afirma que medir os qubits dado na dada base Pauli terá sempre o resultado dado.</span><span class="sxs-lookup"><span data-stu-id="b6f89-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b6f89-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b6f89-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="b6f89-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b6f89-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="b6f89-108">Um efeito de medição para afirmar a probabilidade de, expressa como um operador pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="b6f89-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b6f89-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6f89-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b6f89-110">Um registo para fazer a afirmação.</span><span class="sxs-lookup"><span data-stu-id="b6f89-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="b6f89-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="b6f89-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="b6f89-112">O resultado esperado de `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="b6f89-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="b6f89-113">msg : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b6f89-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b6f89-114">Uma mensagem a ser reportada se a afirmação falhar.</span><span class="sxs-lookup"><span data-stu-id="b6f89-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6f89-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6f89-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b6f89-116">Observações</span><span class="sxs-lookup"><span data-stu-id="b6f89-116">Remarks</span></span>

<span data-ttu-id="b6f89-117">Note que as versões adjacentes e controladas desta operação não verificarão a condição.</span><span class="sxs-lookup"><span data-stu-id="b6f89-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6f89-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b6f89-118">See Also</span></span>

- [<span data-ttu-id="b6f89-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span><span class="sxs-lookup"><span data-stu-id="b6f89-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)