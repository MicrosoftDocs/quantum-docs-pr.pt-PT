---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: Aplicar operação FirstThreeQubitsA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: c3374ceba9f442f9315d4b5fc54b158327124926
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208776"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="63f8f-102">Aplicar operação FirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="63f8f-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="63f8f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63f8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63f8f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63f8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63f8f-105">Aplica uma operação aos três primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="63f8f-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="63f8f-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="63f8f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="63f8f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="63f8f-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-adj"></a><span data-ttu-id="63f8f-108">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) é Adj</span><span class="sxs-lookup"><span data-stu-id="63f8f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="63f8f-109">Uma operação a ser aplicada aos três primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="63f8f-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="63f8f-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="63f8f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="63f8f-111">Qubit array para os primeiros três qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="63f8f-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63f8f-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63f8f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="63f8f-113">Observações</span><span class="sxs-lookup"><span data-stu-id="63f8f-113">Remarks</span></span>

<span data-ttu-id="63f8f-114">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="63f8f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="63f8f-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="63f8f-115">See Also</span></span>

- [<span data-ttu-id="63f8f-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="63f8f-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)