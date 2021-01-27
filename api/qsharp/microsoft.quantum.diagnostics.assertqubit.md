---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AfirmaQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853442"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="d76e5-102">AfirmaQubit</span><span class="sxs-lookup"><span data-stu-id="d76e5-102">AssertQubit operation</span></span>

<span data-ttu-id="d76e5-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d76e5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d76e5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d76e5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d76e5-105">Afirma que o qubit `q` está no estado esperado do operador Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="d76e5-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d76e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d76e5-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="d76e5-107">esperado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="d76e5-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="d76e5-108">Em que estado se espera que o qubit esteja: `Zero` ou `One` .</span><span class="sxs-lookup"><span data-stu-id="d76e5-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="d76e5-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d76e5-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d76e5-110">O qubit cujo estado é afirmado.</span><span class="sxs-lookup"><span data-stu-id="d76e5-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d76e5-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d76e5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d76e5-112">Observações</span><span class="sxs-lookup"><span data-stu-id="d76e5-112">Remarks</span></span>

<span data-ttu-id="d76e5-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite afirmar estados de qubit arbit arbit em vez de apenas $Z dólares.</span><span class="sxs-lookup"><span data-stu-id="d76e5-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="d76e5-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d76e5-114">See Also</span></span>

- [<span data-ttu-id="d76e5-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="d76e5-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)