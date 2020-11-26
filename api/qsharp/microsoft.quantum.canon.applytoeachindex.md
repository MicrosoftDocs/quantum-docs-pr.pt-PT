---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: AplicaçãoToEachIndex operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217618"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="f7f15-102">AplicaçãoToEachIndex operação</span><span class="sxs-lookup"><span data-stu-id="f7f15-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="f7f15-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7f15-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7f15-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7f15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7f15-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="f7f15-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f7f15-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f7f15-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="f7f15-107">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f7f15-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f7f15-108">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="f7f15-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f7f15-109">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f7f15-109">register : 'T[]</span></span>

<span data-ttu-id="f7f15-110">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="f7f15-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7f15-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7f15-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7f15-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f7f15-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7f15-113">'T</span><span class="sxs-lookup"><span data-stu-id="f7f15-113">'T</span></span>

<span data-ttu-id="f7f15-114">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="f7f15-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7f15-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7f15-115">See Also</span></span>

- [<span data-ttu-id="f7f15-116">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f7f15-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="f7f15-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="f7f15-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="f7f15-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="f7f15-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="f7f15-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="f7f15-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)