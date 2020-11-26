---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operação DrawRandomInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192915"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="03bbf-102">Operação DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="03bbf-102">DrawRandomInt operation</span></span>

<span data-ttu-id="03bbf-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="03bbf-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="03bbf-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="03bbf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="03bbf-105">Desenha um inteiro aleatório numa determinada gama inclusiva.</span><span class="sxs-lookup"><span data-stu-id="03bbf-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="03bbf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="03bbf-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="03bbf-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03bbf-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03bbf-108">O menor número inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="03bbf-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="03bbf-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03bbf-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03bbf-110">O maior inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="03bbf-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="03bbf-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03bbf-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03bbf-112">Um inteiro na gama inclusiva de `min` até `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="03bbf-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="03bbf-113">Observações</span><span class="sxs-lookup"><span data-stu-id="03bbf-113">Remarks</span></span>

<span data-ttu-id="03bbf-114">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="03bbf-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="03bbf-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="03bbf-115">See Also</span></span>

- [<span data-ttu-id="03bbf-116">Microsoft.Quantum.DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="03bbf-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)