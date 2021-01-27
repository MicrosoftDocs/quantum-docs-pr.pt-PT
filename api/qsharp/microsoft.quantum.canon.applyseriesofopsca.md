---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Aplicação FuncionamentoSeriesOfOpsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850874"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="ee122-102">Aplicação FuncionamentoSeriesOfOpsCA</span><span class="sxs-lookup"><span data-stu-id="ee122-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="ee122-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee122-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee122-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee122-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee122-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="ee122-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="ee122-106">(Adjacente + Controlado)</span><span class="sxs-lookup"><span data-stu-id="ee122-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ee122-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee122-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="ee122-108">listOfOps : 'T[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl[]</span><span class="sxs-lookup"><span data-stu-id="ee122-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="ee122-109">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="ee122-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="ee122-110">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="ee122-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="ee122-111">Cada um deve ter um functor adjacente e controlado.</span><span class="sxs-lookup"><span data-stu-id="ee122-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="ee122-112">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="ee122-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="ee122-113">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="ee122-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="ee122-114">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="ee122-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="ee122-115">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="ee122-115">register : 'T[]</span></span>

<span data-ttu-id="ee122-116">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="ee122-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee122-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee122-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee122-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ee122-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee122-119">'T</span><span class="sxs-lookup"><span data-stu-id="ee122-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="ee122-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ee122-120">Example</span></span>

<span data-ttu-id="ee122-121">O seguinte aplica-se Exp ([PauliX, PauliY], 0.5) a qubits 0, 1 // depois X a qubit 2 lets = [Exp[PauliX, PauliY], 0,5, _), ApplyToFirstQubitCA(X, _)]; Deixar os índices = [0, 1], [2]]; AplicaçãoSeriesOfOpsCA (ops, índices, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="ee122-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitCA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsCA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="ee122-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ee122-122">See Also</span></span>

- [<span data-ttu-id="ee122-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="ee122-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)