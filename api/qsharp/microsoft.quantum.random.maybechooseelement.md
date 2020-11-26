---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Talvez a operaçãoChooseElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192864"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="3b735-102">Talvez a operaçãoChooseElement</span><span class="sxs-lookup"><span data-stu-id="3b735-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="3b735-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3b735-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3b735-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3b735-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b735-105">Dada uma série de dados e uma distribuição sobre os seus índices, tenta escolher um elemento ao acaso.</span><span class="sxs-lookup"><span data-stu-id="3b735-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="3b735-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3b735-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="3b735-107">dados : 'T[]</span><span class="sxs-lookup"><span data-stu-id="3b735-107">data : 'T[]</span></span>

<span data-ttu-id="3b735-108">A matriz a partir da qual um elemento deve ser escolhido.</span><span class="sxs-lookup"><span data-stu-id="3b735-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="3b735-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="3b735-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="3b735-110">Uma distribuição sobre os índices `data` de.</span><span class="sxs-lookup"><span data-stu-id="3b735-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="3b735-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span><span class="sxs-lookup"><span data-stu-id="3b735-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3b735-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="3b735-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b735-113">'T</span><span class="sxs-lookup"><span data-stu-id="3b735-113">'T</span></span>

