---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Aplicação FuncionamentoSeriesOfOpsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717636"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="453db-102">Aplicação FuncionamentoSeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="453db-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="453db-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="453db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="453db-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="453db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="453db-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="453db-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="453db-106">(Adjacente + Controlado)</span><span class="sxs-lookup"><span data-stu-id="453db-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="453db-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="453db-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="453db-108">listOfOps : 'T[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span><span class="sxs-lookup"><span data-stu-id="453db-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="453db-109">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="453db-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="453db-110">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="453db-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="453db-111">Cada um deve ter um functor adjacente e controlado.</span><span class="sxs-lookup"><span data-stu-id="453db-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="453db-112">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="453db-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="453db-113">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="453db-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="453db-114">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="453db-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="453db-115">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="453db-115">register : 'T[]</span></span>

<span data-ttu-id="453db-116">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="453db-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="453db-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="453db-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="453db-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="453db-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="453db-119">'T</span><span class="sxs-lookup"><span data-stu-id="453db-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="453db-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="453db-120">See Also</span></span>

- [<span data-ttu-id="453db-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="453db-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)