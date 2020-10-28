---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operação DrawRandomDouble
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723985"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="c3156-102">Operação DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c3156-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="c3156-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c3156-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c3156-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3156-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3156-105">Desenha um número real aleatório num determinado intervalo inclusivo.</span><span class="sxs-lookup"><span data-stu-id="c3156-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="c3156-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3156-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="c3156-107">min : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3156-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3156-108">O menor número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="c3156-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="c3156-109">max : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3156-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3156-110">O maior número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="c3156-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="c3156-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3156-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3156-112">Um número real aleatório no intervalo inclusivo de `min` para `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="c3156-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3156-113">Observações</span><span class="sxs-lookup"><span data-stu-id="c3156-113">Remarks</span></span>

<span data-ttu-id="c3156-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="c3156-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3156-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c3156-115">See Also</span></span>

- [<span data-ttu-id="c3156-116">Microsoft.Quantum.ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="c3156-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)