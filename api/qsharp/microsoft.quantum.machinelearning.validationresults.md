---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidaçãoResults tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846082"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="edbd2-102">ValidaçãoResults tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="edbd2-102">ValidationResults user defined type</span></span>

<span data-ttu-id="edbd2-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="edbd2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="edbd2-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="edbd2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="edbd2-105">Os resultados de ter validado um classificador contra um conjunto de amostras.</span><span class="sxs-lookup"><span data-stu-id="edbd2-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="edbd2-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="edbd2-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="edbd2-107">NMisclassificações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edbd2-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edbd2-108">O número de classificações erradas observadas durante a validação.</span><span class="sxs-lookup"><span data-stu-id="edbd2-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="edbd2-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edbd2-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

