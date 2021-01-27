---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Aplicação FuncionaMento DeSeriesOfOps
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841506"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="a8062-102">Aplicação FuncionaMento DeSeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="a8062-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="a8062-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8062-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8062-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8062-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8062-105">Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.</span><span class="sxs-lookup"><span data-stu-id="a8062-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a8062-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a8062-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="a8062-107">listOfOps : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="a8062-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="a8062-108">Lista de ops, cada um tomando uma matriz 'T, a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="a8062-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="a8062-109">São aplicados sequencialmente, o índice mais baixo primeiro.</span><span class="sxs-lookup"><span data-stu-id="a8062-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="a8062-110">alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span><span class="sxs-lookup"><span data-stu-id="a8062-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="a8062-111">Matrizes aninhadas descrevendo os alvos da operação.</span><span class="sxs-lookup"><span data-stu-id="a8062-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="a8062-112">Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.</span><span class="sxs-lookup"><span data-stu-id="a8062-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="a8062-113">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="a8062-113">register : 'T[]</span></span>

<span data-ttu-id="a8062-114">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="a8062-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8062-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8062-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a8062-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a8062-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8062-117">'T</span><span class="sxs-lookup"><span data-stu-id="a8062-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="a8062-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a8062-118">Example</span></span>

<span data-ttu-id="a8062-119">O seguinte aplica-se Exp ([PauliX, PauliY], 0.5) a qubits 0, 1 // depois X a qubit 2 lets = [Exp[PauliX, PauliY], 0,5, _), ApplyToFirstQubit(X, _)]; Deixar os índices = [0, 1], [2]]; AplicaçãoSeriesOfOps (ops, índices, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="a8062-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="a8062-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a8062-120">See Also</span></span>

- [<span data-ttu-id="a8062-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="a8062-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)