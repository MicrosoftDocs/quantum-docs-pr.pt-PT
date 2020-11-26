---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: AplicaçãoSeriesOfOpsA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e5b3527507f79dcc77803ce01472856145df0e9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217973"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="0bb2d-102">AplicaçãoSeriesOfOpsA operação</span><span class="sxs-lookup"><span data-stu-id="0bb2d-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="0bb2d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bb2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bb2d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bb2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bb2d-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="0bb2d-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="0bb2d-106">(Adjacente)</span><span class="sxs-lookup"><span data-stu-id="0bb2d-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0bb2d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0bb2d-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="0bb2d-108">listOfOps : 'T[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj[]</span><span class="sxs-lookup"><span data-stu-id="0bb2d-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="0bb2d-109">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="0bb2d-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="0bb2d-110">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="0bb2d-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="0bb2d-111">Cada um deve ter um functor adjacente</span><span class="sxs-lookup"><span data-stu-id="0bb2d-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="0bb2d-112">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="0bb2d-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="0bb2d-113">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="0bb2d-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="0bb2d-114">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="0bb2d-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="0bb2d-115">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="0bb2d-115">register : 'T[]</span></span>

<span data-ttu-id="0bb2d-116">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="0bb2d-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bb2d-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bb2d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0bb2d-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0bb2d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bb2d-119">'T</span><span class="sxs-lookup"><span data-stu-id="0bb2d-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="0bb2d-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0bb2d-120">See Also</span></span>

- [<span data-ttu-id="0bb2d-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="0bb2d-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)