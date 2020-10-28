---
uid: Microsoft.Quantum.Arrays.Zip
title: Função zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718727"
---
# <a name="zip-function"></a><span data-ttu-id="151f4-102">Função zip</span><span class="sxs-lookup"><span data-stu-id="151f4-102">Zip function</span></span>

<span data-ttu-id="151f4-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="151f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="151f4-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="151f4-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="151f4-105">Zip foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="151f4-105">Zip has been deprecated.</span></span> <span data-ttu-id="151f4-106">Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="151f4-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="151f4-107">Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="151f4-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="151f4-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="151f4-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="151f4-109">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="151f4-109">left : 'T[]</span></span>

<span data-ttu-id="151f4-110">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="151f4-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="151f4-111">direito : 'U[]</span><span class="sxs-lookup"><span data-stu-id="151f4-111">right : 'U[]</span></span>

<span data-ttu-id="151f4-112">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="151f4-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="151f4-113">Saída : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="151f4-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="151f4-114">Uma matriz contendo pares da forma `(left[idx], right[idx])` para cada `idx` um .</span><span class="sxs-lookup"><span data-stu-id="151f4-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="151f4-115">Se as duas matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="151f4-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="151f4-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="151f4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="151f4-117">'T</span><span class="sxs-lookup"><span data-stu-id="151f4-117">'T</span></span>

<span data-ttu-id="151f4-118">O tipo de elementos da matriz esquerda.</span><span class="sxs-lookup"><span data-stu-id="151f4-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="151f4-119">'U</span><span class="sxs-lookup"><span data-stu-id="151f4-119">'U</span></span>

<span data-ttu-id="151f4-120">O tipo de elementos de matriz certos.</span><span class="sxs-lookup"><span data-stu-id="151f4-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="151f4-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="151f4-121">See Also</span></span>

- [<span data-ttu-id="151f4-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="151f4-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="151f4-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="151f4-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="151f4-124">Microsoft.Quantum.Arrays.Unzipped</span><span class="sxs-lookup"><span data-stu-id="151f4-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)