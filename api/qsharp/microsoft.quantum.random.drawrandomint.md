---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operação DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851144"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="db693-102">Operação DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="db693-102">DrawRandomInt operation</span></span>

<span data-ttu-id="db693-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="db693-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="db693-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="db693-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="db693-105">Desenha um inteiro aleatório numa determinada gama inclusiva.</span><span class="sxs-lookup"><span data-stu-id="db693-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="db693-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="db693-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="db693-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db693-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db693-108">O menor número inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="db693-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="db693-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db693-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db693-110">O maior inteiro a ser desenhado.</span><span class="sxs-lookup"><span data-stu-id="db693-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="db693-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db693-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db693-112">Um inteiro na gama inclusiva de `min` até `max` com probabilidade uniforme.</span><span class="sxs-lookup"><span data-stu-id="db693-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="db693-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="db693-113">Example</span></span>

<span data-ttu-id="db693-114">O seguinte corte Q# rola aleatoriamente um die de seis lados:</span><span class="sxs-lookup"><span data-stu-id="db693-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="db693-115">Observações</span><span class="sxs-lookup"><span data-stu-id="db693-115">Remarks</span></span>

<span data-ttu-id="db693-116">Falha se `max <= min` . .</span><span class="sxs-lookup"><span data-stu-id="db693-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="db693-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="db693-117">See Also</span></span>

- [<span data-ttu-id="db693-118">Microsoft.Quantum.DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="db693-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)