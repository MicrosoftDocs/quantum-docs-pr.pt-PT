---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operação IterateThroughCartesianProduct
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206447"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="e7a32-102">Operação IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="e7a32-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="e7a32-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7a32-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7a32-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7a32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7a32-105">Aplica uma operação para cada índice no produto Cartesiano de várias gamas.</span><span class="sxs-lookup"><span data-stu-id="e7a32-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="e7a32-106">Description</span><span class="sxs-lookup"><span data-stu-id="e7a32-106">Description</span></span>

<span data-ttu-id="e7a32-107">Iterativamente aplica uma operação para cada elemento do produto Cartesiano `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` de, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="e7a32-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="e7a32-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7a32-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="e7a32-109">limites : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e7a32-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e7a32-110">Uma matriz que especifica as gamas a serem iteradas, com cada gama a ser especificada como um comprimento inteiro.</span><span class="sxs-lookup"><span data-stu-id="e7a32-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="e7a32-111">op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e7a32-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e7a32-112">Uma operação a ser convocada para cada elemento do produto cartesiano dado.</span><span class="sxs-lookup"><span data-stu-id="e7a32-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7a32-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7a32-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e7a32-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e7a32-114">See Also</span></span>

- [<span data-ttu-id="e7a32-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="e7a32-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)