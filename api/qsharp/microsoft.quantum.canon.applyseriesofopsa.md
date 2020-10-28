---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: AplicaçãoSeriesOfOpsA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717653"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="a402f-102">AplicaçãoSeriesOfOpsA operação</span><span class="sxs-lookup"><span data-stu-id="a402f-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="a402f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a402f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a402f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a402f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a402f-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="a402f-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="a402f-106">(Adjacente)</span><span class="sxs-lookup"><span data-stu-id="a402f-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a402f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a402f-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="a402f-108">listOfOps : 'T[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj[]</span><span class="sxs-lookup"><span data-stu-id="a402f-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="a402f-109">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="a402f-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="a402f-110">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="a402f-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="a402f-111">Cada um deve ter um functor adjacente</span><span class="sxs-lookup"><span data-stu-id="a402f-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="a402f-112">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="a402f-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="a402f-113">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="a402f-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="a402f-114">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="a402f-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="a402f-115">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="a402f-115">register : 'T[]</span></span>

<span data-ttu-id="a402f-116">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="a402f-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a402f-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a402f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a402f-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a402f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a402f-119">'T</span><span class="sxs-lookup"><span data-stu-id="a402f-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="a402f-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a402f-120">See Also</span></span>

- [<span data-ttu-id="a402f-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="a402f-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)