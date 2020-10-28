---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operação IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716040"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="2f174-102">Operação IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="2f174-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="2f174-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f174-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f174-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f174-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f174-105">Aplica uma operação para cada índice no produto Cartesiano de várias gamas.</span><span class="sxs-lookup"><span data-stu-id="2f174-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="2f174-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="2f174-106">Description</span></span>

<span data-ttu-id="2f174-107">Iterativamente aplica uma operação para cada elemento do produto Cartesiano `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` de, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="2f174-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="2f174-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2f174-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="2f174-109">limites : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2f174-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2f174-110">Uma matriz que especifica as gamas a serem iteradas, com cada gama a ser especificada como um comprimento inteiro.</span><span class="sxs-lookup"><span data-stu-id="2f174-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="2f174-111">op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="2f174-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2f174-112">Uma operação a ser convocada para cada elemento do produto cartesiano dado.</span><span class="sxs-lookup"><span data-stu-id="2f174-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f174-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f174-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2f174-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2f174-114">See Also</span></span>

- [<span data-ttu-id="2f174-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="2f174-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)