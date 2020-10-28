---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Aplicação FuncionaMento DeSeriesOfOps
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717667"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="81c36-102">Aplicação FuncionaMento DeSeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="81c36-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="81c36-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81c36-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81c36-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81c36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81c36-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="81c36-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="81c36-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="81c36-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="81c36-107">listOfOps : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="81c36-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="81c36-108">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="81c36-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="81c36-109">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="81c36-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="81c36-110">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="81c36-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="81c36-111">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="81c36-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="81c36-112">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="81c36-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="81c36-113">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="81c36-113">register : 'T[]</span></span>

<span data-ttu-id="81c36-114">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="81c36-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81c36-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81c36-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="81c36-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="81c36-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81c36-117">'T</span><span class="sxs-lookup"><span data-stu-id="81c36-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="81c36-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="81c36-118">See Also</span></span>

- [<span data-ttu-id="81c36-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="81c36-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)