---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Função de distribuição contínua UniformDis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842325"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="df5b2-102">Função de distribuição contínua UniformDis</span><span class="sxs-lookup"><span data-stu-id="df5b2-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="df5b2-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="df5b2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="df5b2-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="df5b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="df5b2-105">Devolve uma distribuição uniforme sobre um determinado intervalo inclusivo.</span><span class="sxs-lookup"><span data-stu-id="df5b2-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="df5b2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="df5b2-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="df5b2-107">min : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df5b2-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df5b2-108">O menor número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="df5b2-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="df5b2-109">max : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df5b2-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df5b2-110">O maior número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="df5b2-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="df5b2-111">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="df5b2-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="df5b2-112">Uma distribuição cujas variações aleatórias são números reais no intervalo inclusivo de `min` para `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="df5b2-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="df5b2-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="df5b2-113">Example</span></span>

<span data-ttu-id="df5b2-114">O seguinte corte Q# desenha aleatoriamente um ângulo entre $0$ e $2 \pi$:</span><span class="sxs-lookup"><span data-stu-id="df5b2-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="df5b2-115">Observações</span><span class="sxs-lookup"><span data-stu-id="df5b2-115">Remarks</span></span>

<span data-ttu-id="df5b2-116">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="df5b2-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="df5b2-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="df5b2-117">See Also</span></span>

- [<span data-ttu-id="df5b2-118">Microsoft.Quantum.DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="df5b2-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)