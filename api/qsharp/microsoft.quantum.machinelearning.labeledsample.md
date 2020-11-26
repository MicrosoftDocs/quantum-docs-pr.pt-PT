---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido pelo utilizador LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196332"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="48a89-102">Tipo definido pelo utilizador LabeledSample</span><span class="sxs-lookup"><span data-stu-id="48a89-102">LabeledSample user defined type</span></span>

<span data-ttu-id="48a89-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48a89-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="48a89-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48a89-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="48a89-105">Uma amostra, rotulada com uma classe à qual pertence essa amostra.</span><span class="sxs-lookup"><span data-stu-id="48a89-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="48a89-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="48a89-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="48a89-107">Características : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="48a89-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="48a89-108">Um vetor de características para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="48a89-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="48a89-109">Etiqueta : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48a89-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48a89-110">Um rótulo inteiro para a classe a que esta amostra pertence.</span><span class="sxs-lookup"><span data-stu-id="48a89-110">An integer label for the class to which this sample belongs.</span></span>