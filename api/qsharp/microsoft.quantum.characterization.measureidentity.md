---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operação MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714965"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="fcdb2-102">Operação MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="fcdb2-102">MeasureIdentity operation</span></span>

<span data-ttu-id="fcdb2-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fcdb2-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="fcdb2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcdb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcdb2-105">Mede o operador de identidade num registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="fcdb2-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="fcdb2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fcdb2-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="fcdb2-107">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fcdb2-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fcdb2-108">O registo a medir.</span><span class="sxs-lookup"><span data-stu-id="fcdb2-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="fcdb2-109">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="fcdb2-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="fcdb2-110">O valor do resultado `Zero` .</span><span class="sxs-lookup"><span data-stu-id="fcdb2-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcdb2-111">Observações</span><span class="sxs-lookup"><span data-stu-id="fcdb2-111">Remarks</span></span>

<span data-ttu-id="fcdb2-112">Uma vez que $\boldone$ tem apenas o valor de $1$, e não tem um valor de eigen negativo, esta operação volta sempre `Zero` , correspondente ao eigenvalue $+1 = (-1)^0$, e não causa um colapso do estado de `register` .</span><span class="sxs-lookup"><span data-stu-id="fcdb2-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="fcdb2-113">Por si só, esta operação não é útil, mas é útil no contexto da tomografia do processo, uma vez que fornece informações sobre a preservação de vestígios de um processo quântico.</span><span class="sxs-lookup"><span data-stu-id="fcdb2-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="fcdb2-114">Em particular, uma máquina-alvo com medição de perda deve substituir esta operação por uma medição real de $\boldone$.</span><span class="sxs-lookup"><span data-stu-id="fcdb2-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>