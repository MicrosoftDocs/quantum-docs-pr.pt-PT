---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operação IterateThroughCartesianProduct
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840269"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="98edd-102">Operação IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="98edd-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="98edd-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98edd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98edd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98edd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98edd-105">Aplica uma operação para cada índice no produto Cartesiano de várias gamas.</span><span class="sxs-lookup"><span data-stu-id="98edd-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="98edd-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="98edd-106">Description</span></span>

<span data-ttu-id="98edd-107">Iterativamente aplica uma operação para cada elemento do produto Cartesiano `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` de, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="98edd-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="98edd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="98edd-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="98edd-109">limites : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98edd-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98edd-110">Uma matriz que especifica as gamas a serem iteradas, com cada gama a ser especificada como um comprimento inteiro.</span><span class="sxs-lookup"><span data-stu-id="98edd-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="98edd-111">op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="98edd-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="98edd-112">Uma operação a ser convocada para cada elemento do produto cartesiano dado.</span><span class="sxs-lookup"><span data-stu-id="98edd-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98edd-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98edd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="98edd-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="98edd-114">Example</span></span>

<span data-ttu-id="98edd-115">Dada uma `op` operação, os dois cortes seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="98edd-115">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a><span data-ttu-id="98edd-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="98edd-116">See Also</span></span>

- [<span data-ttu-id="98edd-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="98edd-117">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)