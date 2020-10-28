---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Função de distribuição dedestribuição dedesemcontinuas transformada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710944"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="e996c-102">Função de distribuição dedestribuição dedesemcontinuas transformada</span><span class="sxs-lookup"><span data-stu-id="e996c-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="e996c-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e996c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e996c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e996c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e996c-105">Dada uma distribuição contínua, devolve uma nova distribuição que transforma o original por uma determinada função.</span><span class="sxs-lookup"><span data-stu-id="e996c-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="e996c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e996c-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="e996c-107">transformar : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e996c-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e996c-108">Uma função que transforma variações da distribuição original à distribuição transformada.</span><span class="sxs-lookup"><span data-stu-id="e996c-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="e996c-109">distribuição : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="e996c-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="e996c-110">A distribuição original a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="e996c-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="e996c-111">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="e996c-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="e996c-112">Uma nova distribuição relacionada com `distribution` a transformação dada `transform` por.</span><span class="sxs-lookup"><span data-stu-id="e996c-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>