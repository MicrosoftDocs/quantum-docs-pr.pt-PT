---
uid: Microsoft.Quantum.Arrays.Zip
title: Função zip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219860"
---
# <a name="zip-function"></a><span data-ttu-id="c1640-102">Função zip</span><span class="sxs-lookup"><span data-stu-id="c1640-102">Zip function</span></span>

<span data-ttu-id="c1640-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c1640-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c1640-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1640-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="c1640-105">Zip foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="c1640-105">Zip has been deprecated.</span></span> <span data-ttu-id="c1640-106">Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="c1640-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="c1640-107">Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="c1640-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="c1640-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1640-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="c1640-109">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="c1640-109">left : 'T[]</span></span>

<span data-ttu-id="c1640-110">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="c1640-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="c1640-111">direito : 'U[]</span><span class="sxs-lookup"><span data-stu-id="c1640-111">right : 'U[]</span></span>

<span data-ttu-id="c1640-112">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="c1640-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="c1640-113">Saída : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="c1640-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="c1640-114">Uma matriz contendo pares da forma `(left[idx], right[idx])` para cada `idx` um .</span><span class="sxs-lookup"><span data-stu-id="c1640-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="c1640-115">Se as duas matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="c1640-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c1640-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c1640-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1640-117">'T</span><span class="sxs-lookup"><span data-stu-id="c1640-117">'T</span></span>

<span data-ttu-id="c1640-118">O tipo de elementos da matriz esquerda.</span><span class="sxs-lookup"><span data-stu-id="c1640-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="c1640-119">'U</span><span class="sxs-lookup"><span data-stu-id="c1640-119">'U</span></span>

<span data-ttu-id="c1640-120">O tipo de elementos de matriz certos.</span><span class="sxs-lookup"><span data-stu-id="c1640-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1640-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c1640-121">See Also</span></span>

- [<span data-ttu-id="c1640-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="c1640-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="c1640-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="c1640-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="c1640-124">Microsoft.Quantum.Arrays.Unzipped</span><span class="sxs-lookup"><span data-stu-id="c1640-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)