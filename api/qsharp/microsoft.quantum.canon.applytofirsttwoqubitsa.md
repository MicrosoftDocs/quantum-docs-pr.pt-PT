---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Aplicar operação FirstTwoQubitsA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 1a286c167a87372dc89d62ab3733b186298c43a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208708"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="e6b26-102">Aplicar operação FirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="e6b26-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="e6b26-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6b26-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6b26-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6b26-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6b26-105">Aplica uma operação aos dois primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="e6b26-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="e6b26-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="e6b26-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="e6b26-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e6b26-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="e6b26-108">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)= [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj</span><span class="sxs-lookup"><span data-stu-id="e6b26-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e6b26-109">Uma operação a ser aplicada aos dois primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="e6b26-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e6b26-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6b26-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e6b26-111">Qubit array para os dois primeiros qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="e6b26-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6b26-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6b26-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e6b26-113">Observações</span><span class="sxs-lookup"><span data-stu-id="e6b26-113">Remarks</span></span>

<span data-ttu-id="e6b26-114">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="e6b26-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="e6b26-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e6b26-115">See Also</span></span>

- [<span data-ttu-id="e6b26-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="e6b26-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)