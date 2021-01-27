---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operação DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847613"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="6f07f-102">Operação DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="6f07f-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="6f07f-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6f07f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6f07f-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6f07f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6f07f-105">Desenha um número real aleatório num determinado intervalo inclusivo.</span><span class="sxs-lookup"><span data-stu-id="6f07f-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="6f07f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6f07f-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="6f07f-107">min : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f07f-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f07f-108">O menor número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="6f07f-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="6f07f-109">max : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f07f-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f07f-110">O maior número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="6f07f-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="6f07f-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f07f-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f07f-112">Um número real aleatório no intervalo inclusivo de `min` para `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="6f07f-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="6f07f-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6f07f-113">Example</span></span>

<span data-ttu-id="6f07f-114">O seguinte corte Q# desenha aleatoriamente um ângulo entre $0$ e $2 \pi$:</span><span class="sxs-lookup"><span data-stu-id="6f07f-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="6f07f-115">Observações</span><span class="sxs-lookup"><span data-stu-id="6f07f-115">Remarks</span></span>

<span data-ttu-id="6f07f-116">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="6f07f-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f07f-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6f07f-117">See Also</span></span>

- [<span data-ttu-id="6f07f-118">Microsoft.Quantum.ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="6f07f-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)