---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: Função ExtendedGreatestCommonDivisorL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1445f1c3d2a5852459a492fa5e6bfd2a685786d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857538"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="db10a-102">Função ExtendedGreatestCommonDivisorL</span><span class="sxs-lookup"><span data-stu-id="db10a-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="db10a-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="db10a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="db10a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db10a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db10a-105">Computa um tuple $(u,v)$ tal que $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, onde $\operatorname{GCD}$ é $a$ maior divisor comum de $a$ e $b$.</span><span class="sxs-lookup"><span data-stu-id="db10a-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="db10a-106">O GCD é sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="db10a-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="db10a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="db10a-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="db10a-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="db10a-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="db10a-109">o primeiro número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="db10a-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="db10a-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="db10a-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="db10a-111">o segundo número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="db10a-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="db10a-112">Saída :[(BigInt,](xref:microsoft.quantum.lang-ref.bigint)[BigInt)](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="db10a-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="db10a-113">Tuple $(u,v)$ com a propriedade $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span><span class="sxs-lookup"><span data-stu-id="db10a-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="db10a-114">Referências</span><span class="sxs-lookup"><span data-stu-id="db10a-114">References</span></span>

- <span data-ttu-id="db10a-115">Esta implementação é de acordo com https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="db10a-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>