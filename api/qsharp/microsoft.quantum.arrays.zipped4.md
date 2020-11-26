---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Função Zipped4
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219639"
---
# <a name="zipped4-function"></a><span data-ttu-id="69b2c-102">Função Zipped4</span><span class="sxs-lookup"><span data-stu-id="69b2c-102">Zipped4 function</span></span>

<span data-ttu-id="69b2c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="69b2c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="69b2c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69b2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69b2c-105">Dado quatro matrizes, devolve uma nova matriz de 4 tuples de modo que cada 4 tuple contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="69b2c-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="69b2c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="69b2c-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="69b2c-107">primeiro : 'T1].</span><span class="sxs-lookup"><span data-stu-id="69b2c-107">first : 'T1[]</span></span>

<span data-ttu-id="69b2c-108">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="69b2c-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="69b2c-109">segundo : 'T2]]</span><span class="sxs-lookup"><span data-stu-id="69b2c-109">second : 'T2[]</span></span>

<span data-ttu-id="69b2c-110">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="69b2c-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="69b2c-111">terceiro: 'T3]]</span><span class="sxs-lookup"><span data-stu-id="69b2c-111">third : 'T3[]</span></span>

<span data-ttu-id="69b2c-112">Uma matriz contendo valores para o terceiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="69b2c-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="69b2c-113">quarto : 'T4]]</span><span class="sxs-lookup"><span data-stu-id="69b2c-113">fourth : 'T4[]</span></span>

<span data-ttu-id="69b2c-114">Uma matriz contendo valores para o quarto elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="69b2c-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="69b2c-115">Saída: ('T1,'T2,'T3,'T4)[]</span><span class="sxs-lookup"><span data-stu-id="69b2c-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="69b2c-116">Uma matriz contendo 4 tuples da forma `(first[idx], second[idx], third[idx], fourth[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="69b2c-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="69b2c-117">Se as quatro matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="69b2c-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="69b2c-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="69b2c-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="69b2c-119">'T1</span><span class="sxs-lookup"><span data-stu-id="69b2c-119">'T1</span></span>

<span data-ttu-id="69b2c-120">O tipo de primeiros elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="69b2c-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="69b2c-121">'T2</span><span class="sxs-lookup"><span data-stu-id="69b2c-121">'T2</span></span>

<span data-ttu-id="69b2c-122">O tipo de elementos da segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="69b2c-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="69b2c-123">'T3</span><span class="sxs-lookup"><span data-stu-id="69b2c-123">'T3</span></span>

<span data-ttu-id="69b2c-124">O tipo de elementos da terceira matriz.</span><span class="sxs-lookup"><span data-stu-id="69b2c-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="69b2c-125">'T4</span><span class="sxs-lookup"><span data-stu-id="69b2c-125">'T4</span></span>

<span data-ttu-id="69b2c-126">O tipo de elementos da quarta matriz.</span><span class="sxs-lookup"><span data-stu-id="69b2c-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="69b2c-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="69b2c-127">See Also</span></span>

- [<span data-ttu-id="69b2c-128">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="69b2c-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="69b2c-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="69b2c-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)