---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Função InferredLabels
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722484"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="69f7c-102">Função InferredLabels</span><span class="sxs-lookup"><span data-stu-id="69f7c-102">InferredLabels function</span></span>

<span data-ttu-id="69f7c-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="69f7c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="69f7c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69f7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69f7c-105">Dada uma série de probabilidades de classificação e um enviesamento, devolve o rótulo inferido de cada probabilidade.</span><span class="sxs-lookup"><span data-stu-id="69f7c-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="69f7c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="69f7c-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="69f7c-107">parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69f7c-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69f7c-108">O preconceito entre duas classes, normalmente o resultado do treino de um classificador.</span><span class="sxs-lookup"><span data-stu-id="69f7c-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="69f7c-109">probabilidades : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="69f7c-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="69f7c-110">Uma série de probabilidades de classificação para um conjunto de amostras, normalmente resultantes da estimativa de frequências de classificação.</span><span class="sxs-lookup"><span data-stu-id="69f7c-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="69f7c-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="69f7c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="69f7c-112">O rótulo deduzido de cada probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="69f7c-112">The label inferred from each classification probability.</span></span>