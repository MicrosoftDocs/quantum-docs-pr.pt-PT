---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Aplicação OperaçãoToFirstTwoQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717314"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="ae01b-102">Aplicação OperaçãoToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="ae01b-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="ae01b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae01b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae01b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae01b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae01b-105">Aplica uma operação aos dois primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="ae01b-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ae01b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ae01b-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="ae01b-107">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)= [unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ae01b-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ae01b-108">Uma operação a ser aplicada aos dois primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="ae01b-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="ae01b-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ae01b-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ae01b-110">Qubit array para os dois primeiros qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="ae01b-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae01b-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae01b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ae01b-112">Observações</span><span class="sxs-lookup"><span data-stu-id="ae01b-112">Remarks</span></span>

<span data-ttu-id="ae01b-113">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="ae01b-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="ae01b-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ae01b-114">See Also</span></span>

- [<span data-ttu-id="ae01b-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="ae01b-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="ae01b-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="ae01b-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="ae01b-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="ae01b-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)