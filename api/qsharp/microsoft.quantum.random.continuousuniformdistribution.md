---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Função de distribuição contínua UniformDis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193085"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="e46ed-102">Função de distribuição contínua UniformDis</span><span class="sxs-lookup"><span data-stu-id="e46ed-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="e46ed-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e46ed-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e46ed-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e46ed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e46ed-105">Devolve uma distribuição uniforme sobre um determinado intervalo inclusivo.</span><span class="sxs-lookup"><span data-stu-id="e46ed-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="e46ed-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e46ed-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="e46ed-107">min : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e46ed-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e46ed-108">O menor número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="e46ed-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="e46ed-109">max : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e46ed-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e46ed-110">O maior número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="e46ed-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="e46ed-111">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="e46ed-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="e46ed-112">Uma distribuição cujas variações aleatórias são números reais no intervalo inclusivo de `min` para `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="e46ed-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="e46ed-113">Observações</span><span class="sxs-lookup"><span data-stu-id="e46ed-113">Remarks</span></span>

<span data-ttu-id="e46ed-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="e46ed-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e46ed-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e46ed-115">See Also</span></span>

- [<span data-ttu-id="e46ed-116">Microsoft.Quantum.DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="e46ed-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)