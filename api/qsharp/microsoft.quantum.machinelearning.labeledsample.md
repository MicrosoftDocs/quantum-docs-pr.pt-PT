---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido pelo utilizador LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846968"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="87992-102">Tipo definido pelo utilizador LabeledSample</span><span class="sxs-lookup"><span data-stu-id="87992-102">LabeledSample user defined type</span></span>

<span data-ttu-id="87992-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="87992-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="87992-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="87992-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="87992-105">Uma amostra, rotulada com uma classe à qual pertence essa amostra.</span><span class="sxs-lookup"><span data-stu-id="87992-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="87992-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="87992-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="87992-107">Características : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="87992-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="87992-108">Um vetor de características para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="87992-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="87992-109">Etiqueta : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87992-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87992-110">Um rótulo inteiro para a classe a que esta amostra pertence.</span><span class="sxs-lookup"><span data-stu-id="87992-110">An integer label for the class to which this sample belongs.</span></span>