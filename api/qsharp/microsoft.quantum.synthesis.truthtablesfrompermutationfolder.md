---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: Função TruthTablesFromPermutationFolder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 881bb8e29d3d7761cc521837502ea79b0714b381
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855256"
---
# <a name="truthtablesfrompermutationfolder-function"></a><span data-ttu-id="c9fdf-102">Função TruthTablesFromPermutationFolder</span><span class="sxs-lookup"><span data-stu-id="c9fdf-102">TruthTablesFromPermutationFolder function</span></span>

<span data-ttu-id="c9fdf-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c9fdf-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c9fdf-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9fdf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9fdf-105">Lógica de decomposição para um único índice variável</span><span class="sxs-lookup"><span data-stu-id="c9fdf-105">Decomposition logic for a single variable index</span></span>

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a><span data-ttu-id="c9fdf-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9fdf-106">Description</span></span>

<span data-ttu-id="c9fdf-107">Isto toma o estado atual e gera uma permutação atualizada e possivelmente adiciona novas funções para portões controlados.</span><span class="sxs-lookup"><span data-stu-id="c9fdf-107">This takes the current state and generates an updated permutation and possibly adds new functions for controlled gates.</span></span>

## <a name="input"></a><span data-ttu-id="c9fdf-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c9fdf-108">Input</span></span>

### <a name="numvars--int"></a><span data-ttu-id="c9fdf-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9fdf-109">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="state--decompositionstate"></a><span data-ttu-id="c9fdf-110">estado : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="c9fdf-110">state : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>




### <a name="index--int"></a><span data-ttu-id="c9fdf-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9fdf-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--decompositionstate"></a><span data-ttu-id="c9fdf-112">Saída : [DecomposiçãoState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span><span class="sxs-lookup"><span data-stu-id="c9fdf-112">Output : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)</span></span>

