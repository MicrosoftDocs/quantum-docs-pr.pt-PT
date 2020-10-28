---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operação DrawRandomInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724657"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="5cd64-102">Operação DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="5cd64-102">DrawRandomInt operation</span></span>

<span data-ttu-id="5cd64-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5cd64-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5cd64-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5cd64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5cd64-105">Desenha um inteiro aleatório numa determinada gama inclusiva.</span><span class="sxs-lookup"><span data-stu-id="5cd64-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5cd64-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5cd64-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="5cd64-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5cd64-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5cd64-108">O menor número inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5cd64-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="5cd64-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5cd64-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5cd64-110">O maior inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="5cd64-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="5cd64-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5cd64-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5cd64-112">Um inteiro na gama inclusiva de `min` até `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="5cd64-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cd64-113">Observações</span><span class="sxs-lookup"><span data-stu-id="5cd64-113">Remarks</span></span>

<span data-ttu-id="5cd64-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="5cd64-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cd64-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5cd64-115">See Also</span></span>

- [<span data-ttu-id="5cd64-116">Microsoft.Quantum.DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="5cd64-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)