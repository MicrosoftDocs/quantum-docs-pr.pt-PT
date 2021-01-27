---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Função InferredLabel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848426"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="a98a6-102">Função InferredLabel</span><span class="sxs-lookup"><span data-stu-id="a98a6-102">InferredLabel function</span></span>

<span data-ttu-id="a98a6-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a98a6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a98a6-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a98a6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a98a6-105">Dada a probabilidade de classificação e um enviesamento, devolve o rótulo inferido dessa probabilidade.</span><span class="sxs-lookup"><span data-stu-id="a98a6-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="a98a6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a98a6-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="a98a6-107">parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a98a6-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a98a6-108">O preconceito entre duas classes, normalmente o resultado do treino de um classificador.</span><span class="sxs-lookup"><span data-stu-id="a98a6-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="a98a6-109">probabilidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a98a6-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a98a6-110">Uma probabilidade de classificação para uma determinada amostra, tipicamente resultante da estimativa da sua frequência de classificação.</span><span class="sxs-lookup"><span data-stu-id="a98a6-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="a98a6-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a98a6-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a98a6-112">O rótulo deduzido da dada probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="a98a6-112">The label inferred from the given classification probability.</span></span>