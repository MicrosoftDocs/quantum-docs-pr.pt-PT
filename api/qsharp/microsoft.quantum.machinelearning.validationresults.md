---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidaçãoResults tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211496"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="0e4c6-102">ValidaçãoResults tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="0e4c6-102">ValidationResults user defined type</span></span>

<span data-ttu-id="0e4c6-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0e4c6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0e4c6-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0e4c6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0e4c6-105">Os resultados de ter validado um classificador contra um conjunto de amostras.</span><span class="sxs-lookup"><span data-stu-id="0e4c6-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="0e4c6-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="0e4c6-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="0e4c6-107">NMisclassificações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e4c6-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e4c6-108">O número de classificações erradas observadas durante a validação.</span><span class="sxs-lookup"><span data-stu-id="0e4c6-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="0e4c6-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e4c6-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

