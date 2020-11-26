---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Função de distribuição DiscreteUniformD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193017"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="8bcb5-102">Função de distribuição DiscreteUniformD</span><span class="sxs-lookup"><span data-stu-id="8bcb5-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="8bcb5-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="8bcb5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="8bcb5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8bcb5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8bcb5-105">Devolve uma distribuição uniforme sobre uma determinada gama inclusiva.</span><span class="sxs-lookup"><span data-stu-id="8bcb5-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="8bcb5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8bcb5-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="8bcb5-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8bcb5-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8bcb5-108">O menor número inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="8bcb5-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="8bcb5-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8bcb5-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8bcb5-110">O maior inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="8bcb5-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="8bcb5-111">Saída : [Distribuição discreta](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="8bcb5-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="8bcb5-112">Uma distribuição cujas variações aleatórias são inteiros na gama inclusiva de `min` até `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="8bcb5-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bcb5-113">Observações</span><span class="sxs-lookup"><span data-stu-id="8bcb5-113">Remarks</span></span>

<span data-ttu-id="8bcb5-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="8bcb5-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bcb5-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8bcb5-115">See Also</span></span>

- [<span data-ttu-id="8bcb5-116">Microsoft.Quantum.DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="8bcb5-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)