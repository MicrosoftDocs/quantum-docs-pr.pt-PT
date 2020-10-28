---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Função de classificações erradas
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723579"
---
# <a name="misclassifications-function"></a><span data-ttu-id="2deb2-102">Função de classificações erradas</span><span class="sxs-lookup"><span data-stu-id="2deb2-102">Misclassifications function</span></span>

<span data-ttu-id="2deb2-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2deb2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2deb2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2deb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2deb2-105">Dado um conjunto de etiquetas inferidas e um conjunto de etiquetas corretas, os índices de reposição para o local onde cada conjunto de rótulos difere.</span><span class="sxs-lookup"><span data-stu-id="2deb2-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="2deb2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2deb2-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="2deb2-107">inferiuLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2deb2-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2deb2-108">As etiquetas inferidas para um determinado conjunto de formação ou validação.</span><span class="sxs-lookup"><span data-stu-id="2deb2-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="2deb2-109">realLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2deb2-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2deb2-110">Os verdadeiros rótulos para um determinado conjunto de treino ou validação.</span><span class="sxs-lookup"><span data-stu-id="2deb2-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="2deb2-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2deb2-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2deb2-112">Uma série de índices `idx` tal `inferredLabels[idx] != actualLabels[idx]` que.</span><span class="sxs-lookup"><span data-stu-id="2deb2-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>