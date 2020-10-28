---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Aplicação Operação FirstThreeQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717384"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="f6aba-102">Aplicação Operação FirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="f6aba-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="f6aba-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f6aba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f6aba-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6aba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6aba-105">Aplica uma operação aos três primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="f6aba-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f6aba-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f6aba-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="f6aba-107">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit](xref:microsoft.quantum.lang-ref.qubit)) = [> Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6aba-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f6aba-108">Uma operação a ser aplicada aos três primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="f6aba-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="f6aba-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f6aba-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f6aba-110">Qubit array para os primeiros três qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="f6aba-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f6aba-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6aba-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f6aba-112">Observações</span><span class="sxs-lookup"><span data-stu-id="f6aba-112">Remarks</span></span>

<span data-ttu-id="f6aba-113">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="f6aba-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="f6aba-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f6aba-114">See Also</span></span>

- [<span data-ttu-id="f6aba-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="f6aba-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="f6aba-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="f6aba-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="f6aba-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="f6aba-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)