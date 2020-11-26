---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operação DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192949"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="5cf81-102">Operação DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="5cf81-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="5cf81-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5cf81-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5cf81-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5cf81-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5cf81-105">Desenha um número real aleatório num determinado intervalo inclusivo.</span><span class="sxs-lookup"><span data-stu-id="5cf81-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="5cf81-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5cf81-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="5cf81-107">min : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cf81-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cf81-108">O menor número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5cf81-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="5cf81-109">max : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cf81-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cf81-110">O maior número real a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5cf81-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="5cf81-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cf81-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cf81-112">Um número real aleatório no intervalo inclusivo de `min` para `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="5cf81-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cf81-113">Observações</span><span class="sxs-lookup"><span data-stu-id="5cf81-113">Remarks</span></span>

<span data-ttu-id="5cf81-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="5cf81-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cf81-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5cf81-115">See Also</span></span>

- [<span data-ttu-id="5cf81-116">Microsoft.Quantum.ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="5cf81-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)