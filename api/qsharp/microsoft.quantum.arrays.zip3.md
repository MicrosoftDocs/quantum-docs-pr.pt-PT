---
uid: Microsoft.Quantum.Arrays.Zip3
title: Função Zip3
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845358"
---
# <a name="zip3-function"></a><span data-ttu-id="7e08c-102">Função Zip3</span><span class="sxs-lookup"><span data-stu-id="7e08c-102">Zip3 function</span></span>

<span data-ttu-id="7e08c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7e08c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7e08c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e08c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="7e08c-105">Zip3 foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="7e08c-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="7e08c-106">Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped3> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="7e08c-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="7e08c-107">Tendo em conta três matrizes, devolve uma nova matriz de 3 tuples de modo a que cada 3 tuple contenha um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="7e08c-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="7e08c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7e08c-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="7e08c-109">primeiro : 'T1].</span><span class="sxs-lookup"><span data-stu-id="7e08c-109">first : 'T1[]</span></span>

<span data-ttu-id="7e08c-110">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="7e08c-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="7e08c-111">segundo : 'T2]]</span><span class="sxs-lookup"><span data-stu-id="7e08c-111">second : 'T2[]</span></span>

<span data-ttu-id="7e08c-112">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="7e08c-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="7e08c-113">terceiro: 'T3]]</span><span class="sxs-lookup"><span data-stu-id="7e08c-113">third : 'T3[]</span></span>

<span data-ttu-id="7e08c-114">Uma matriz contendo valores para o terceiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="7e08c-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="7e08c-115">Saída : ('T1,'T2,'T3)[]</span><span class="sxs-lookup"><span data-stu-id="7e08c-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="7e08c-116">Uma matriz contendo 3 tuples da forma `(first[idx], second[idx], third[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="7e08c-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="7e08c-117">Se as três matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="7e08c-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7e08c-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7e08c-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="7e08c-119">'T1</span><span class="sxs-lookup"><span data-stu-id="7e08c-119">'T1</span></span>

<span data-ttu-id="7e08c-120">O tipo de primeiros elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="7e08c-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="7e08c-121">'T2</span><span class="sxs-lookup"><span data-stu-id="7e08c-121">'T2</span></span>

<span data-ttu-id="7e08c-122">O tipo de elementos da segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="7e08c-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="7e08c-123">'T3</span><span class="sxs-lookup"><span data-stu-id="7e08c-123">'T3</span></span>

<span data-ttu-id="7e08c-124">O tipo de elementos da terceira matriz.</span><span class="sxs-lookup"><span data-stu-id="7e08c-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e08c-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7e08c-125">See Also</span></span>

- [<span data-ttu-id="7e08c-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="7e08c-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="7e08c-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="7e08c-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)