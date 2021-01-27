---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: Aplicação Operação FirstThreeQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: b01c1072306cfdebcb90827a14683a32312481fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850690"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="0cb3b-102">Aplicação Operação FirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="0cb3b-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="0cb3b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0cb3b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0cb3b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cb3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cb3b-105">Aplica uma operação aos três primeiros qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0cb3b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0cb3b-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="0cb3b-107">op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit](xref:microsoft.quantum.lang-ref.qubit)) = [> Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cb3b-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0cb3b-108">Uma operação a ser aplicada aos três primeiros qubits</span><span class="sxs-lookup"><span data-stu-id="0cb3b-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0cb3b-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0cb3b-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0cb3b-110">Qubit array para os primeiros três qubits dos quais a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cb3b-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cb3b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0cb3b-112">Observações</span><span class="sxs-lookup"><span data-stu-id="0cb3b-112">Remarks</span></span>

<span data-ttu-id="0cb3b-113">Isto equivale a:</span><span class="sxs-lookup"><span data-stu-id="0cb3b-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="0cb3b-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0cb3b-114">See Also</span></span>

- [<span data-ttu-id="0cb3b-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="0cb3b-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="0cb3b-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="0cb3b-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="0cb3b-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="0cb3b-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)