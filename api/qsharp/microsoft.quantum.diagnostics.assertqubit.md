---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AfirmaQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712946"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="8f9e8-102">AfirmaQubit</span><span class="sxs-lookup"><span data-stu-id="8f9e8-102">AssertQubit operation</span></span>

<span data-ttu-id="8f9e8-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8f9e8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8f9e8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f9e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f9e8-105">Afirma que o qubit `q` está no estado esperado do operador Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8f9e8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8f9e8-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="8f9e8-107">esperado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="8f9e8-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="8f9e8-108">Em que estado se espera que o qubit esteja: `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="8f9e8-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="8f9e8-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8f9e8-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8f9e8-110">O qubit cujo estado é afirmado.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f9e8-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f9e8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8f9e8-112">Observações</span><span class="sxs-lookup"><span data-stu-id="8f9e8-112">Remarks</span></span>

<span data-ttu-id="8f9e8-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite afirmar estados de qubit arbit arbit em vez de apenas $Z dólares.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f9e8-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8f9e8-114">See Also</span></span>

- [<span data-ttu-id="8f9e8-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="8f9e8-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)