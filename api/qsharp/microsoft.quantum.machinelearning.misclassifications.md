---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Função de classificações erradas
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853932"
---
# <a name="misclassifications-function"></a><span data-ttu-id="abc4c-102">Função de classificações erradas</span><span class="sxs-lookup"><span data-stu-id="abc4c-102">Misclassifications function</span></span>

<span data-ttu-id="abc4c-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="abc4c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="abc4c-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="abc4c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="abc4c-105">Dado um conjunto de etiquetas inferidas e um conjunto de etiquetas corretas, os índices de reposição para o local onde cada conjunto de rótulos difere.</span><span class="sxs-lookup"><span data-stu-id="abc4c-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="abc4c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="abc4c-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="abc4c-107">inferiuLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="abc4c-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="abc4c-108">As etiquetas inferidas para um determinado conjunto de formação ou validação.</span><span class="sxs-lookup"><span data-stu-id="abc4c-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="abc4c-109">realLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="abc4c-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="abc4c-110">Os verdadeiros rótulos para um determinado conjunto de treino ou validação.</span><span class="sxs-lookup"><span data-stu-id="abc4c-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="abc4c-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="abc4c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="abc4c-112">Uma série de índices `idx` tal `inferredLabels[idx] != actualLabels[idx]` que.</span><span class="sxs-lookup"><span data-stu-id="abc4c-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="abc4c-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="abc4c-113">Example</span></span>

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```