---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Função TruthTablesFromPermutationFolder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724458"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="a4e2a-102">Função TruthTablesFromPermutationFolder</span><span class="sxs-lookup"><span data-stu-id="a4e2a-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="a4e2a-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a4e2a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a4e2a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4e2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4e2a-105">Lógica de decomposição para um único índice variável</span><span class="sxs-lookup"><span data-stu-id="a4e2a-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="a4e2a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4e2a-106">Description</span></span>

<span data-ttu-id="a4e2a-107">Isto toma o estado atual e gera uma permutação atualizada e possivelmente adiciona novas funções para portões controlados.</span><span class="sxs-lookup"><span data-stu-id="a4e2a-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="a4e2a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a4e2a-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="a4e2a-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4e2a-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="a4e2a-110">estado : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="a4e2a-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="a4e2a-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a4e2a-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="a4e2a-112">Saída : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="a4e2a-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

