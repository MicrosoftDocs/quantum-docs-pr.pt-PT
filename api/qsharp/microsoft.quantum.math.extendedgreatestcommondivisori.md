---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Função ExtendedGreatestCommonDivisorI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e86237f39e696485a3496f1c6dd571cd516214ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857542"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="da6d1-102">Função ExtendedGreatestCommonDivisorI</span><span class="sxs-lookup"><span data-stu-id="da6d1-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="da6d1-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="da6d1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="da6d1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da6d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da6d1-105">Computa um tuple $(u,v)$ tal que $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, onde $\operatorname{GCD}$ é $a$ maior divisor comum de $a$ e $b$.</span><span class="sxs-lookup"><span data-stu-id="da6d1-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="da6d1-106">O GCD é sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="da6d1-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="da6d1-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="da6d1-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="da6d1-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da6d1-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da6d1-109">o primeiro número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="da6d1-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="da6d1-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da6d1-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da6d1-111">o segundo número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="da6d1-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="da6d1-112">Saída : ([Int](xref:microsoft.quantum.lang-ref.int),[Int)](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da6d1-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="da6d1-113">Tuple $(u,v)$ com a propriedade $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span><span class="sxs-lookup"><span data-stu-id="da6d1-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="da6d1-114">Referências</span><span class="sxs-lookup"><span data-stu-id="da6d1-114">References</span></span>

- <span data-ttu-id="da6d1-115">Esta implementação é de acordo com https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="da6d1-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>