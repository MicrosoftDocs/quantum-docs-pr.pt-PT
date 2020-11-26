---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Aplicação FuncionaMento DeSeriesOfOps
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218007"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="205c7-102">Aplicação FuncionaMento DeSeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="205c7-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="205c7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="205c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="205c7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="205c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="205c7-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="205c7-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="205c7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="205c7-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="205c7-107">listOfOps : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="205c7-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="205c7-108">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="205c7-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="205c7-109">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="205c7-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="205c7-110">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="205c7-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="205c7-111">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="205c7-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="205c7-112">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="205c7-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="205c7-113">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="205c7-113">register : 'T[]</span></span>

<span data-ttu-id="205c7-114">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="205c7-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="205c7-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="205c7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="205c7-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="205c7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="205c7-117">'T</span><span class="sxs-lookup"><span data-stu-id="205c7-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="205c7-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="205c7-118">See Also</span></span>

- [<span data-ttu-id="205c7-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="205c7-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)