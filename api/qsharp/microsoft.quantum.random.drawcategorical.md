---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operação DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193000"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="bf7c5-102">Operação DrawCategorical</span><span class="sxs-lookup"><span data-stu-id="bf7c5-102">DrawCategorical operation</span></span>

<span data-ttu-id="bf7c5-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="bf7c5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="bf7c5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bf7c5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bf7c5-105">Extrai uma amostra aleatória de uma distribuição categórica especificada por uma lista de probablidades.</span><span class="sxs-lookup"><span data-stu-id="bf7c5-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="bf7c5-106">Description</span><span class="sxs-lookup"><span data-stu-id="bf7c5-106">Description</span></span>

<span data-ttu-id="bf7c5-107">A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice.</span><span class="sxs-lookup"><span data-stu-id="bf7c5-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="bf7c5-108">Elementos de matriz que são iguais a zero são ignorados e os seus índices nunca são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="bf7c5-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="bf7c5-109">Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for maior que zero, então a operação falha.</span><span class="sxs-lookup"><span data-stu-id="bf7c5-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="bf7c5-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="bf7c5-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="bf7c5-111">probs : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bf7c5-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bf7c5-112">Uma matriz de números de pontos flutuantes proporcional à probabilidade de selecionar cada índice.</span><span class="sxs-lookup"><span data-stu-id="bf7c5-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="bf7c5-113">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf7c5-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf7c5-114">Um inteiro $i$ com probabilidade $\Pr(i) = p_i / \sum_i p_i$, onde $p_i$ é o elemento $i$th de `probs` .</span><span class="sxs-lookup"><span data-stu-id="bf7c5-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf7c5-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bf7c5-115">See Also</span></span>

- [<span data-ttu-id="bf7c5-116">Microsoft.Quantum.Random.CategoricalDistribution</span><span class="sxs-lookup"><span data-stu-id="bf7c5-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)