---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidaçãoResults tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720430"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="945d4-102">ValidaçãoResults tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="945d4-102">ValidationResults user defined type</span></span>

<span data-ttu-id="945d4-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="945d4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="945d4-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="945d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="945d4-105">Os resultados de ter validado um classificador contra um conjunto de amostras.</span><span class="sxs-lookup"><span data-stu-id="945d4-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="945d4-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="945d4-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="945d4-107">NMisclassificações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="945d4-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="945d4-108">O número de classificações erradas observadas durante a validação.</span><span class="sxs-lookup"><span data-stu-id="945d4-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="945d4-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="945d4-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

