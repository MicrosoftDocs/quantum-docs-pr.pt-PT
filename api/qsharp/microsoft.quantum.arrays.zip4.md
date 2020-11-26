---
uid: Microsoft.Quantum.Arrays.Zip4
title: Função Zip4
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: c9dd07ddc63f1d75952d3841997eed0f78e054b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219792"
---
# <a name="zip4-function"></a><span data-ttu-id="4afb7-102">Função Zip4</span><span class="sxs-lookup"><span data-stu-id="4afb7-102">Zip4 function</span></span>

<span data-ttu-id="4afb7-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4afb7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4afb7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4afb7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="4afb7-105">Zip4 foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="4afb7-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="4afb7-106">Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped4> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="4afb7-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="4afb7-107">Dado quatro matrizes, devolve uma nova matriz de 4 tuples de modo que cada 4 tuple contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="4afb7-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="4afb7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4afb7-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="4afb7-109">primeiro : 'T1].</span><span class="sxs-lookup"><span data-stu-id="4afb7-109">first : 'T1[]</span></span>

<span data-ttu-id="4afb7-110">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="4afb7-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="4afb7-111">segundo : 'T2]]</span><span class="sxs-lookup"><span data-stu-id="4afb7-111">second : 'T2[]</span></span>

<span data-ttu-id="4afb7-112">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="4afb7-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="4afb7-113">terceiro: 'T3]]</span><span class="sxs-lookup"><span data-stu-id="4afb7-113">third : 'T3[]</span></span>

<span data-ttu-id="4afb7-114">Uma matriz contendo valores para o terceiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="4afb7-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="4afb7-115">quarto : 'T4]]</span><span class="sxs-lookup"><span data-stu-id="4afb7-115">fourth : 'T4[]</span></span>

<span data-ttu-id="4afb7-116">Uma matriz contendo valores para o quarto elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="4afb7-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="4afb7-117">Saída: ('T1,'T2,'T3,'T4)[]</span><span class="sxs-lookup"><span data-stu-id="4afb7-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="4afb7-118">Uma matriz contendo 4 tuples da forma `(first[idx], second[idx], third[idx], fourth[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="4afb7-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="4afb7-119">Se as quatro matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="4afb7-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4afb7-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4afb7-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="4afb7-121">'T1</span><span class="sxs-lookup"><span data-stu-id="4afb7-121">'T1</span></span>

<span data-ttu-id="4afb7-122">O tipo de primeiros elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="4afb7-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="4afb7-123">'T2</span><span class="sxs-lookup"><span data-stu-id="4afb7-123">'T2</span></span>

<span data-ttu-id="4afb7-124">O tipo de elementos da segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="4afb7-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="4afb7-125">'T3</span><span class="sxs-lookup"><span data-stu-id="4afb7-125">'T3</span></span>

<span data-ttu-id="4afb7-126">O tipo de elementos da terceira matriz.</span><span class="sxs-lookup"><span data-stu-id="4afb7-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="4afb7-127">'T4</span><span class="sxs-lookup"><span data-stu-id="4afb7-127">'T4</span></span>

<span data-ttu-id="4afb7-128">O tipo de elementos da quarta matriz.</span><span class="sxs-lookup"><span data-stu-id="4afb7-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="4afb7-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4afb7-129">See Also</span></span>

- [<span data-ttu-id="4afb7-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="4afb7-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="4afb7-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="4afb7-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)