---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202197"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="1dd78-102">AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="1dd78-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="1dd78-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1dd78-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1dd78-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1dd78-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1dd78-105">Afirma que o qubit `q` está no estado esperado do operador Pauli Z até uma certa tolerância.</span><span class="sxs-lookup"><span data-stu-id="1dd78-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="1dd78-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1dd78-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="1dd78-107">esperado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="1dd78-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="1dd78-108">Em que estado se espera que o qubit esteja: `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="1dd78-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="1dd78-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1dd78-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1dd78-110">O qubit cujo estado é afirmado.</span><span class="sxs-lookup"><span data-stu-id="1dd78-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1dd78-111">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1dd78-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1dd78-112">Tolerância na probabilidade de uma medição do qubit devolvendo o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="1dd78-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1dd78-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1dd78-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1dd78-114">Observações</span><span class="sxs-lookup"><span data-stu-id="1dd78-114">Remarks</span></span>

<span data-ttu-id="1dd78-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite afirmar estados de qubit arbit arbit em vez de apenas $Z dólares.</span><span class="sxs-lookup"><span data-stu-id="1dd78-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dd78-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1dd78-116">See Also</span></span>

- [<span data-ttu-id="1dd78-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="1dd78-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)