---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido pelo utilizador LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711336"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="b6f30-102">Tipo definido pelo utilizador LabeledSample</span><span class="sxs-lookup"><span data-stu-id="b6f30-102">LabeledSample user defined type</span></span>

<span data-ttu-id="b6f30-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b6f30-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b6f30-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6f30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6f30-105">Uma amostra, rotulada com uma classe à qual pertence essa amostra.</span><span class="sxs-lookup"><span data-stu-id="b6f30-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="b6f30-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="b6f30-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="b6f30-107">Características : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b6f30-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b6f30-108">Um vetor de características para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="b6f30-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="b6f30-109">Etiqueta : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6f30-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6f30-110">Um rótulo inteiro para a classe a que esta amostra pertence.</span><span class="sxs-lookup"><span data-stu-id="b6f30-110">An integer label for the class to which this sample belongs.</span></span>