---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: Aplicação FuncionamentoSeriesOfOpsC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717650"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="059f6-102">Aplicação FuncionamentoSeriesOfOpsC</span><span class="sxs-lookup"><span data-stu-id="059f6-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="059f6-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="059f6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="059f6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="059f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="059f6-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="059f6-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="059f6-106">(Controlado)</span><span class="sxs-lookup"><span data-stu-id="059f6-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="059f6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="059f6-107">Input</span></span>

### <a name="listofops--t--unit-ctl"></a><span data-ttu-id="059f6-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span><span class="sxs-lookup"><span data-stu-id="059f6-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="059f6-109">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="059f6-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="059f6-110">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="059f6-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="059f6-111">Cada um deve ter um functor controlado</span><span class="sxs-lookup"><span data-stu-id="059f6-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="059f6-112">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="059f6-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="059f6-113">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="059f6-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="059f6-114">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="059f6-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="059f6-115">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="059f6-115">register : 'T[]</span></span>

<span data-ttu-id="059f6-116">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="059f6-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="059f6-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="059f6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="059f6-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="059f6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="059f6-119">'T</span><span class="sxs-lookup"><span data-stu-id="059f6-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="059f6-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="059f6-120">See Also</span></span>

- [<span data-ttu-id="059f6-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="059f6-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)