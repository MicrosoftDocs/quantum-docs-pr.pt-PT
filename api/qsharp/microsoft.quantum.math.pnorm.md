---
uid: Microsoft.Quantum.Math.PNorm
title: Função PNorm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722302"
---
# <a name="pnorm-function"></a><span data-ttu-id="8652c-102">Função PNorm</span><span class="sxs-lookup"><span data-stu-id="8652c-102">PNorm function</span></span>

<span data-ttu-id="8652c-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8652c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8652c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8652c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8652c-105">Devolve a `L(p)` norma de um vetor de `Double` s.</span><span class="sxs-lookup"><span data-stu-id="8652c-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="8652c-106">Ou seja, dado um conjunto $x$ de `Double[]` tipo, isto devolve o $p$-norm $ \| x \| \_ p= (\sum_{j}[x_j^{p})^{1/p}$.</span><span class="sxs-lookup"><span data-stu-id="8652c-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="8652c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8652c-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="8652c-108">p : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8652c-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8652c-109">O expoente $p$ na norma de $p dólares.</span><span class="sxs-lookup"><span data-stu-id="8652c-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="8652c-110">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8652c-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="8652c-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8652c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8652c-112">O $p $-norm $ \| x \| _p$.</span><span class="sxs-lookup"><span data-stu-id="8652c-112">The $p$-norm $\|x\|_p$.</span></span>