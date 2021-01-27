---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: Aplicar operação FirstTwoQubitsA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 197f1da6682b100a0b71f3548727188c0ef6f7c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850683"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="9b8c4-102">Aplicar operação FirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="9b8c4-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="9b8c4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b8c4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b8c4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b8c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b8c4-105">Aplica uma operação aos dois primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="9b8c4-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="9b8c4-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="9b8c4-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9b8c4-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="9b8c4-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="9b8c4-108">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)= [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj</span><span class="sxs-lookup"><span data-stu-id="9b8c4-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9b8c4-109">Uma operação a ser aplicada aos dois primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="9b8c4-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="9b8c4-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9b8c4-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9b8c4-111">Qubit array para os dois primeiros qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="9b8c4-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b8c4-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b8c4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9b8c4-113">Observações</span><span class="sxs-lookup"><span data-stu-id="9b8c4-113">Remarks</span></span>

<span data-ttu-id="9b8c4-114">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="9b8c4-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="9b8c4-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9b8c4-115">See Also</span></span>

- [<span data-ttu-id="9b8c4-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="9b8c4-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)