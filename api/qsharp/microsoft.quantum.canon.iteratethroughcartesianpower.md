---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operação IterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716026"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="4c0c5-102">Operação IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="4c0c5-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="4c0c5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4c0c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4c0c5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c0c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c0c5-105">Aplica uma operação para cada índice na potência cartesiana de uma gama de inteiros.</span><span class="sxs-lookup"><span data-stu-id="4c0c5-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="4c0c5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c0c5-106">Description</span></span>

<span data-ttu-id="4c0c5-107">Iterativamente aplica uma operação para cada elemento de uma potência cartesiana da gama `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="4c0c5-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="4c0c5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4c0c5-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="4c0c5-109">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c0c5-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c0c5-110">O poder cartesiano para o qual o alcance `0..(bound - 1)` deve ser elevado.</span><span class="sxs-lookup"><span data-stu-id="4c0c5-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="4c0c5-111">vinculado : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c0c5-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c0c5-112">Uma especificação da gama a ser iterada, dada como o comprimento da gama.</span><span class="sxs-lookup"><span data-stu-id="4c0c5-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="4c0c5-113">op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4c0c5-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4c0c5-114">Uma operação a ser convocada para cada elemento do poder cartesiano dado.</span><span class="sxs-lookup"><span data-stu-id="4c0c5-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c0c5-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c0c5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4c0c5-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4c0c5-116">See Also</span></span>

- [<span data-ttu-id="4c0c5-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="4c0c5-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)