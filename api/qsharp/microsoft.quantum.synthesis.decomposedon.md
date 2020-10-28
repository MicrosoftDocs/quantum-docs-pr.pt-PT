---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Função decompostaOn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725217"
---
# <a name="decomposedon-function"></a><span data-ttu-id="06020-102">Função decompostaOn</span><span class="sxs-lookup"><span data-stu-id="06020-102">DecomposedOn function</span></span>

<span data-ttu-id="06020-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="06020-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="06020-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06020-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06020-105">Decompõe-se uma permutação numa variável</span><span class="sxs-lookup"><span data-stu-id="06020-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="06020-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="06020-106">Description</span></span>

<span data-ttu-id="06020-107">Dada uma permutação $\pi$ `perm` e um índice $i$ ( ), este método devolve três `index` permutações $(\pi_l, \pi_r), \pi')$ de tal forma que as imagens de $\pi_l$ e $\pi_r$ não mudam bits nos seus elementos em índices que não $i$ e imagens de $\pi'$ não mudam um pouco $i$ nos seus elementos.</span><span class="sxs-lookup"><span data-stu-id="06020-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="06020-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="06020-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="06020-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="06020-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="06020-110">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06020-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="06020-111">Saída :[(Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="06020-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

