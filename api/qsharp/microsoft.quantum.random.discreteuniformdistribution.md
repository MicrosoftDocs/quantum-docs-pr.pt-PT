---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Função de distribuição DiscreteUniformD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853726"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="df3aa-102">Função de distribuição DiscreteUniformD</span><span class="sxs-lookup"><span data-stu-id="df3aa-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="df3aa-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="df3aa-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="df3aa-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="df3aa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="df3aa-105">Devolve uma distribuição uniforme sobre uma determinada gama inclusiva.</span><span class="sxs-lookup"><span data-stu-id="df3aa-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="df3aa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="df3aa-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="df3aa-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df3aa-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df3aa-108">O menor número inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="df3aa-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="df3aa-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df3aa-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df3aa-110">O maior inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="df3aa-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="df3aa-111">Saída : [Distribuição discreta](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="df3aa-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="df3aa-112">Uma distribuição cujas variações aleatórias são inteiros na gama inclusiva de `min` até `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="df3aa-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="df3aa-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="df3aa-113">Example</span></span>

<span data-ttu-id="df3aa-114">O seguinte corte Q# rola aleatoriamente um die de seis lados:</span><span class="sxs-lookup"><span data-stu-id="df3aa-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="df3aa-115">Observações</span><span class="sxs-lookup"><span data-stu-id="df3aa-115">Remarks</span></span>

<span data-ttu-id="df3aa-116">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="df3aa-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="df3aa-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="df3aa-117">See Also</span></span>

- [<span data-ttu-id="df3aa-118">Microsoft.Quantum.DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="df3aa-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)