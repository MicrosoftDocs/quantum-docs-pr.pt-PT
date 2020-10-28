---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: Aplicação Operação FirstThreeQubitsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717373"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="54eb8-102">Aplicação Operação FirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="54eb8-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="54eb8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54eb8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54eb8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54eb8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54eb8-105">Aplica uma operação aos três primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="54eb8-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="54eb8-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="54eb8-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="54eb8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="54eb8-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-ctl"></a><span data-ttu-id="54eb8-108">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="54eb8-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="54eb8-109">Uma operação a ser aplicada aos três primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="54eb8-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="54eb8-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="54eb8-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="54eb8-111">Qubit array para os primeiros três qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="54eb8-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54eb8-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54eb8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="54eb8-113">Observações</span><span class="sxs-lookup"><span data-stu-id="54eb8-113">Remarks</span></span>

<span data-ttu-id="54eb8-114">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="54eb8-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="54eb8-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="54eb8-115">See Also</span></span>

- [<span data-ttu-id="54eb8-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="54eb8-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)