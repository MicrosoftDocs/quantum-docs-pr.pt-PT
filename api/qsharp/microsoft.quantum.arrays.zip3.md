---
uid: Microsoft.Quantum.Arrays.Zip3
title: Função Zip3
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219826"
---
# <a name="zip3-function"></a><span data-ttu-id="b78cf-102">Função Zip3</span><span class="sxs-lookup"><span data-stu-id="b78cf-102">Zip3 function</span></span>

<span data-ttu-id="b78cf-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b78cf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b78cf-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b78cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="b78cf-105">Zip3 foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="b78cf-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="b78cf-106">Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped3> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="b78cf-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="b78cf-107">Tendo em conta três matrizes, devolve uma nova matriz de 3 tuples de modo a que cada 3 tuple contenha um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="b78cf-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b78cf-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b78cf-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b78cf-109">primeiro : 'T1].</span><span class="sxs-lookup"><span data-stu-id="b78cf-109">first : 'T1[]</span></span>

<span data-ttu-id="b78cf-110">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="b78cf-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b78cf-111">segundo : 'T2]]</span><span class="sxs-lookup"><span data-stu-id="b78cf-111">second : 'T2[]</span></span>

<span data-ttu-id="b78cf-112">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="b78cf-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b78cf-113">terceiro: 'T3]]</span><span class="sxs-lookup"><span data-stu-id="b78cf-113">third : 'T3[]</span></span>

<span data-ttu-id="b78cf-114">Uma matriz contendo valores para o terceiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="b78cf-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b78cf-115">Saída : ('T1,'T2,'T3)[]</span><span class="sxs-lookup"><span data-stu-id="b78cf-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b78cf-116">Uma matriz contendo 3 tuples da forma `(first[idx], second[idx], third[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="b78cf-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b78cf-117">Se as três matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="b78cf-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b78cf-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b78cf-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b78cf-119">'T1</span><span class="sxs-lookup"><span data-stu-id="b78cf-119">'T1</span></span>

<span data-ttu-id="b78cf-120">O tipo de primeiros elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="b78cf-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b78cf-121">'T2</span><span class="sxs-lookup"><span data-stu-id="b78cf-121">'T2</span></span>

<span data-ttu-id="b78cf-122">O tipo de elementos da segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="b78cf-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b78cf-123">'T3</span><span class="sxs-lookup"><span data-stu-id="b78cf-123">'T3</span></span>

<span data-ttu-id="b78cf-124">O tipo de elementos da terceira matriz.</span><span class="sxs-lookup"><span data-stu-id="b78cf-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b78cf-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b78cf-125">See Also</span></span>

- [<span data-ttu-id="b78cf-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="b78cf-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="b78cf-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="b78cf-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)