---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: AplicarToach
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844628"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="4dad4-102">AplicarToach</span><span class="sxs-lookup"><span data-stu-id="4dad4-102">ApplyToEach operation</span></span>

<span data-ttu-id="4dad4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4dad4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4dad4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4dad4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4dad4-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="4dad4-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4dad4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4dad4-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="4dad4-107">singleElementOperação : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4dad4-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4dad4-108">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="4dad4-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="4dad4-109">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4dad4-109">register : 'T[]</span></span>

<span data-ttu-id="4dad4-110">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="4dad4-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4dad4-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4dad4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4dad4-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4dad4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4dad4-113">'T</span><span class="sxs-lookup"><span data-stu-id="4dad4-113">'T</span></span>

<span data-ttu-id="4dad4-114">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="4dad4-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="4dad4-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4dad4-115">Example</span></span>

<span data-ttu-id="4dad4-116">Prepare um estado de três qubits $\ket{+}$ estado:</span><span class="sxs-lookup"><span data-stu-id="4dad4-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="4dad4-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4dad4-117">See Also</span></span>

- [<span data-ttu-id="4dad4-118">Microsoft.Quantum.Canon.ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="4dad4-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="4dad4-119">Microsoft.quantum.canon.applyToEacha</span><span class="sxs-lookup"><span data-stu-id="4dad4-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="4dad4-120">Microsoft.Quantum.Canon.ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="4dad4-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)