---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Função InferredLabel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722515"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="8604a-102">Função InferredLabel</span><span class="sxs-lookup"><span data-stu-id="8604a-102">InferredLabel function</span></span>

<span data-ttu-id="8604a-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8604a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8604a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8604a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8604a-105">Dada a probabilidade de classificação e um enviesamento, devolve o rótulo inferido dessa probabilidade.</span><span class="sxs-lookup"><span data-stu-id="8604a-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="8604a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8604a-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="8604a-107">parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8604a-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8604a-108">O preconceito entre duas classes, normalmente o resultado do treino de um classificador.</span><span class="sxs-lookup"><span data-stu-id="8604a-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="8604a-109">probabilidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8604a-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8604a-110">Uma probabilidade de classificação para uma determinada amostra, tipicamente resultante da estimativa da sua frequência de classificação.</span><span class="sxs-lookup"><span data-stu-id="8604a-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="8604a-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8604a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8604a-112">O rótulo deduzido da dada probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="8604a-112">The label inferred from the given classification probability.</span></span>