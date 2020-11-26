---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Aplicar operação FirstTwoQubitsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a2281776b617d5c3f8cc706ea09d14995fce4a27
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208657"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="61385-102">Aplicar operação FirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="61385-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="61385-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61385-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61385-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61385-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61385-105">Aplica uma operação aos dois primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="61385-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="61385-106">O modificador `CA` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="61385-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="61385-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="61385-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="61385-108">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)= [> Unit](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="61385-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="61385-109">Uma operação a ser aplicada aos dois primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="61385-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="61385-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="61385-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="61385-111">Qubit array para os dois primeiros qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="61385-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61385-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61385-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="61385-113">Observações</span><span class="sxs-lookup"><span data-stu-id="61385-113">Remarks</span></span>

<span data-ttu-id="61385-114">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="61385-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="61385-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="61385-115">See Also</span></span>

- [<span data-ttu-id="61385-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="61385-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)