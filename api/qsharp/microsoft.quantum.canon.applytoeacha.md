---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: AplicarToachA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844609"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="f85b5-102">AplicarToachA operação</span><span class="sxs-lookup"><span data-stu-id="f85b5-102">ApplyToEachA operation</span></span>

<span data-ttu-id="f85b5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f85b5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f85b5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f85b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f85b5-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="f85b5-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="f85b5-106">O modificador `A` indica que a operação de um único qubit é adjacente.</span><span class="sxs-lookup"><span data-stu-id="f85b5-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f85b5-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f85b5-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="f85b5-108">singleElementOperação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="f85b5-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f85b5-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="f85b5-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f85b5-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f85b5-110">register : 'T[]</span></span>

<span data-ttu-id="f85b5-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="f85b5-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f85b5-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f85b5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f85b5-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f85b5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f85b5-114">'T</span><span class="sxs-lookup"><span data-stu-id="f85b5-114">'T</span></span>

<span data-ttu-id="f85b5-115">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="f85b5-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="f85b5-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f85b5-116">Example</span></span>

<span data-ttu-id="f85b5-117">Prepare um estado de três qubits $\ket{+}$ estado:</span><span class="sxs-lookup"><span data-stu-id="f85b5-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="f85b5-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f85b5-118">See Also</span></span>

- [<span data-ttu-id="f85b5-119">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f85b5-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)