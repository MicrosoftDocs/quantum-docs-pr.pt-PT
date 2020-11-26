---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Função de classificações NMisclassificações
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196315"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="ade25-102">Função de classificações NMisclassificações</span><span class="sxs-lookup"><span data-stu-id="ade25-102">NMisclassifications function</span></span>

<span data-ttu-id="ade25-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ade25-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ade25-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ade25-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ade25-105">Tendo em conta um conjunto de rótulos inferidos e um conjunto de etiquetas corretas, o número de índices em que cada conjunto de rótulos difere.</span><span class="sxs-lookup"><span data-stu-id="ade25-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="ade25-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ade25-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="ade25-107">proposto : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ade25-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="ade25-108">real : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ade25-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="ade25-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ade25-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ade25-110">O número de índices `idx` tal que `inferredLabels[idx] != actualLabels[idx]` . .</span><span class="sxs-lookup"><span data-stu-id="ade25-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>