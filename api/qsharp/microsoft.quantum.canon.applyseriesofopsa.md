---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: AplicaçãoSeriesOfOpsA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844654"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="70416-102">AplicaçãoSeriesOfOpsA operação</span><span class="sxs-lookup"><span data-stu-id="70416-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="70416-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70416-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70416-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70416-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70416-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="70416-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="70416-106">(Adjacente)</span><span class="sxs-lookup"><span data-stu-id="70416-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="70416-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="70416-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="70416-108">listOfOps : 'T[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj[]</span><span class="sxs-lookup"><span data-stu-id="70416-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="70416-109">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="70416-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="70416-110">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="70416-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="70416-111">Cada um deve ter um functor adjacente</span><span class="sxs-lookup"><span data-stu-id="70416-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="70416-112">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="70416-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="70416-113">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="70416-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="70416-114">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="70416-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="70416-115">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="70416-115">register : 'T[]</span></span>

<span data-ttu-id="70416-116">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="70416-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70416-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70416-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="70416-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="70416-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70416-119">'T</span><span class="sxs-lookup"><span data-stu-id="70416-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="70416-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="70416-120">Example</span></span>

<span data-ttu-id="70416-121">O seguinte aplica-se Exp ([PauliX, PauliY], 0,5) a qubits 0, 1 // depois X a qubit 2 lets = [Exp[PauliX, PauliY], 0,5, _), ApplyToFirstQubitA(X, _)]; Deixar os índices = [0, 1], [2]]; AplicaçãoSeriesOfOpsA (ops, índices, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="70416-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="70416-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="70416-122">See Also</span></span>

- [<span data-ttu-id="70416-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="70416-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)