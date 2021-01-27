---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Função de distribuição dedestribuição dedesemcontinuas transformada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857761"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="83544-102">Função de distribuição dedestribuição dedesemcontinuas transformada</span><span class="sxs-lookup"><span data-stu-id="83544-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="83544-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="83544-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="83544-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="83544-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="83544-105">Dada uma distribuição contínua, devolve uma nova distribuição que transforma o original por uma determinada função.</span><span class="sxs-lookup"><span data-stu-id="83544-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="83544-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="83544-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="83544-107">transformar : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83544-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83544-108">Uma função que transforma variações da distribuição original à distribuição transformada.</span><span class="sxs-lookup"><span data-stu-id="83544-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="83544-109">distribuição : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="83544-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="83544-110">A distribuição original a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="83544-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="83544-111">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="83544-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="83544-112">Uma nova distribuição relacionada com `distribution` a transformação dada `transform` por.</span><span class="sxs-lookup"><span data-stu-id="83544-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="83544-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="83544-113">Example</span></span>

<span data-ttu-id="83544-114">As duas seguintes distribuições são idênticas:</span><span class="sxs-lookup"><span data-stu-id="83544-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```