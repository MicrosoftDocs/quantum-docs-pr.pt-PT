---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Aplicar operação FirstTwoQubitsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717261"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="90dc2-102">Aplicar operação FirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="90dc2-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="90dc2-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="90dc2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="90dc2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90dc2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90dc2-105">Aplica uma operação aos dois primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="90dc2-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="90dc2-106">O modificador `CA` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="90dc2-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="90dc2-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="90dc2-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="90dc2-108">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)=> [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="90dc2-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="90dc2-109">Uma operação a ser aplicada aos dois primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="90dc2-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="90dc2-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="90dc2-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="90dc2-111">Qubit array para os dois primeiros qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="90dc2-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90dc2-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90dc2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="90dc2-113">Observações</span><span class="sxs-lookup"><span data-stu-id="90dc2-113">Remarks</span></span>

<span data-ttu-id="90dc2-114">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="90dc2-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="90dc2-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="90dc2-115">See Also</span></span>

- [<span data-ttu-id="90dc2-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="90dc2-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)