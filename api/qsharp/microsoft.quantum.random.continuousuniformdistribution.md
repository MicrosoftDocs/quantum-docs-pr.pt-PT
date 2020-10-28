---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Função de distribuição contínua UniformDis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709432"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="ee3ce-102">Função de distribuição contínua UniformDis</span><span class="sxs-lookup"><span data-stu-id="ee3ce-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="ee3ce-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ee3ce-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ee3ce-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee3ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee3ce-105">Devolve uma distribuição uniforme sobre um determinado intervalo inclusivo.</span><span class="sxs-lookup"><span data-stu-id="ee3ce-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="ee3ce-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee3ce-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="ee3ce-107">min : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee3ce-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee3ce-108">O menor número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="ee3ce-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="ee3ce-109">max : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee3ce-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee3ce-110">O maior número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="ee3ce-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="ee3ce-111">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="ee3ce-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="ee3ce-112">Uma distribuição cujas variações aleatórias são números reais no intervalo inclusivo de `min` para `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="ee3ce-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee3ce-113">Observações</span><span class="sxs-lookup"><span data-stu-id="ee3ce-113">Remarks</span></span>

<span data-ttu-id="ee3ce-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="ee3ce-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee3ce-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ee3ce-115">See Also</span></span>

- [<span data-ttu-id="ee3ce-116">Microsoft.Quantum.DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="ee3ce-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)