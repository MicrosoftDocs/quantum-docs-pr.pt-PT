---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Função Zipped3
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: c0535ca4d6e0de13bf809a21e69d100dcb798d1f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718691"
---
# <a name="zipped3-function"></a><span data-ttu-id="07a55-102">Função Zipped3</span><span class="sxs-lookup"><span data-stu-id="07a55-102">Zipped3 function</span></span>

<span data-ttu-id="07a55-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="07a55-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="07a55-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07a55-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07a55-105">Tendo em conta três matrizes, devolve uma nova matriz de 3 tuples de modo a que cada 3 tuple contenha um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="07a55-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="07a55-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="07a55-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="07a55-107">primeiro : 'T1].</span><span class="sxs-lookup"><span data-stu-id="07a55-107">first : 'T1[]</span></span>

<span data-ttu-id="07a55-108">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="07a55-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="07a55-109">segundo : 'T2]]</span><span class="sxs-lookup"><span data-stu-id="07a55-109">second : 'T2[]</span></span>

<span data-ttu-id="07a55-110">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="07a55-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="07a55-111">terceiro: 'T3]]</span><span class="sxs-lookup"><span data-stu-id="07a55-111">third : 'T3[]</span></span>

<span data-ttu-id="07a55-112">Uma matriz contendo valores para o terceiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="07a55-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="07a55-113">Saída : ('T1,'T2,'T3)[]</span><span class="sxs-lookup"><span data-stu-id="07a55-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="07a55-114">Uma matriz contendo 3 tuples da forma `(first[idx], second[idx], third[idx])` para cada `idx` .</span><span class="sxs-lookup"><span data-stu-id="07a55-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="07a55-115">Se as três matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="07a55-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07a55-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="07a55-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="07a55-117">'T1</span><span class="sxs-lookup"><span data-stu-id="07a55-117">'T1</span></span>

<span data-ttu-id="07a55-118">O tipo de primeiros elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="07a55-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="07a55-119">'T2</span><span class="sxs-lookup"><span data-stu-id="07a55-119">'T2</span></span>

<span data-ttu-id="07a55-120">O tipo de elementos da segunda matriz.</span><span class="sxs-lookup"><span data-stu-id="07a55-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="07a55-121">'T3</span><span class="sxs-lookup"><span data-stu-id="07a55-121">'T3</span></span>

<span data-ttu-id="07a55-122">O tipo de elementos da terceira matriz.</span><span class="sxs-lookup"><span data-stu-id="07a55-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="07a55-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="07a55-123">See Also</span></span>

- [<span data-ttu-id="07a55-124">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="07a55-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="07a55-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="07a55-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)