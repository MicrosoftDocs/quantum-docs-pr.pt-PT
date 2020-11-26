---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operação MeasureIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216120"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="d96e5-102">Operação MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="d96e5-102">MeasureIdentity operation</span></span>

<span data-ttu-id="d96e5-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d96e5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d96e5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d96e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d96e5-105">Mede o operador de identidade num registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="d96e5-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="d96e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d96e5-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="d96e5-107">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d96e5-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d96e5-108">O registo a medir.</span><span class="sxs-lookup"><span data-stu-id="d96e5-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d96e5-109">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="d96e5-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d96e5-110">O valor do resultado `Zero` .</span><span class="sxs-lookup"><span data-stu-id="d96e5-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d96e5-111">Observações</span><span class="sxs-lookup"><span data-stu-id="d96e5-111">Remarks</span></span>

<span data-ttu-id="d96e5-112">Uma vez que $\boldone$ tem apenas o valor de $1$, e não tem um valor de eigen negativo, esta operação volta sempre `Zero` , correspondente ao eigenvalue $+1 = (-1)^0$, e não causa um colapso do estado de `register` .</span><span class="sxs-lookup"><span data-stu-id="d96e5-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="d96e5-113">Por si só, esta operação não é útil, mas é útil no contexto da tomografia do processo, uma vez que fornece informações sobre a preservação de vestígios de um processo quântico.</span><span class="sxs-lookup"><span data-stu-id="d96e5-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="d96e5-114">Em particular, uma máquina-alvo com medição de perda deve substituir esta operação por uma medição real de $\boldone$.</span><span class="sxs-lookup"><span data-stu-id="d96e5-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>