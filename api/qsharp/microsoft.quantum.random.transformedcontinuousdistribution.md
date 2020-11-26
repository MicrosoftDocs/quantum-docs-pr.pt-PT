---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Função de distribuição dedestribuição dedesemcontinuas transformada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226269"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="16703-102">Função de distribuição dedestribuição dedesemcontinuas transformada</span><span class="sxs-lookup"><span data-stu-id="16703-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="16703-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="16703-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="16703-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16703-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16703-105">Dada uma distribuição contínua, devolve uma nova distribuição que transforma o original por uma determinada função.</span><span class="sxs-lookup"><span data-stu-id="16703-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="16703-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="16703-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="16703-107">transformar : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16703-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="16703-108">Uma função que transforma variações da distribuição original à distribuição transformada.</span><span class="sxs-lookup"><span data-stu-id="16703-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="16703-109">distribuição : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="16703-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="16703-110">A distribuição original a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="16703-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="16703-111">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="16703-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="16703-112">Uma nova distribuição relacionada com `distribution` a transformação dada `transform` por.</span><span class="sxs-lookup"><span data-stu-id="16703-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>