---
uid: Microsoft.Quantum.Math.PNormalized
title: Função PNormalizada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722288"
---
# <a name="pnormalized-function"></a><span data-ttu-id="1b555-102">Função PNormalizada</span><span class="sxs-lookup"><span data-stu-id="1b555-102">PNormalized function</span></span>

<span data-ttu-id="1b555-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1b555-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1b555-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b555-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b555-105">Normaliza um vetor de `Double` s na `L(p)` norma.</span><span class="sxs-lookup"><span data-stu-id="1b555-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="1b555-106">Isto é, dado um conjunto $x$ de `Double[]` tipo, este retorna um conjunto onde todos os elementos são divididos pela norma de $p$ \| x \| _p$.</span><span class="sxs-lookup"><span data-stu-id="1b555-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="1b555-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b555-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="1b555-108">p : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b555-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b555-109">O expoente $p$ na norma de $p dólares.</span><span class="sxs-lookup"><span data-stu-id="1b555-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="1b555-110">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1b555-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="1b555-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1b555-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1b555-112">A matriz $x$ normalizada pela norma de $p$-norm $ \| x \| _p$.</span><span class="sxs-lookup"><span data-stu-id="1b555-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b555-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1b555-113">See Also</span></span>

- [<span data-ttu-id="1b555-114">Microsoft.Quantum.Math.PNorm</span><span class="sxs-lookup"><span data-stu-id="1b555-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)