---
uid: Microsoft.Quantum.Math.PNormalized
title: Função PNormalizada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854838"
---
# <a name="pnormalized-function"></a><span data-ttu-id="0d898-102">Função PNormalizada</span><span class="sxs-lookup"><span data-stu-id="0d898-102">PNormalized function</span></span>

<span data-ttu-id="0d898-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0d898-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0d898-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d898-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d898-105">Normaliza um vetor de `Double` s na `L(p)` norma.</span><span class="sxs-lookup"><span data-stu-id="0d898-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="0d898-106">Isto é, dado um conjunto $x$ de `Double[]` tipo, este retorna um conjunto onde todos os elementos são divididos pela norma de $p$ \| x \| _p$.</span><span class="sxs-lookup"><span data-stu-id="0d898-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="0d898-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d898-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="0d898-108">p : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d898-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d898-109">O expoente $p$ na norma de $p dólares.</span><span class="sxs-lookup"><span data-stu-id="0d898-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="0d898-110">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0d898-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="0d898-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0d898-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0d898-112">A matriz $x$ normalizada pela norma de $p$-norm $ \| x \| _p$.</span><span class="sxs-lookup"><span data-stu-id="0d898-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d898-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0d898-113">See Also</span></span>

- [<span data-ttu-id="0d898-114">Microsoft.Quantum.Math.PNorm</span><span class="sxs-lookup"><span data-stu-id="0d898-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)