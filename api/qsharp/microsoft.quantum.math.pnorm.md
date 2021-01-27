---
uid: Microsoft.Quantum.Math.PNorm
title: Função PNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847656"
---
# <a name="pnorm-function"></a><span data-ttu-id="06e28-102">Função PNorm</span><span class="sxs-lookup"><span data-stu-id="06e28-102">PNorm function</span></span>

<span data-ttu-id="06e28-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="06e28-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="06e28-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06e28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06e28-105">Devolve a `L(p)` norma de um vetor de `Double` s.</span><span class="sxs-lookup"><span data-stu-id="06e28-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="06e28-106">Ou seja, dado um conjunto $x$ de tipo `Double[]` , isto devolve o $p$-norm $ x \| \| \_ p= (\sum_{j}|x_j|^{p})^{1/p}$.</span><span class="sxs-lookup"><span data-stu-id="06e28-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="06e28-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="06e28-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="06e28-108">p : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06e28-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06e28-109">O expoente $p$ na norma de $p dólares.</span><span class="sxs-lookup"><span data-stu-id="06e28-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="06e28-110">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="06e28-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="06e28-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06e28-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06e28-112">O $p $-norm $ \| x \| _p$.</span><span class="sxs-lookup"><span data-stu-id="06e28-112">The $p$-norm $\|x\|_p$.</span></span>