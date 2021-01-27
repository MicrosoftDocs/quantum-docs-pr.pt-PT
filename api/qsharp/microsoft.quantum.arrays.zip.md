---
uid: Microsoft.Quantum.Arrays.Zip
title: Função zip
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850907"
---
# <a name="zip-function"></a><span data-ttu-id="23e7d-102">Função zip</span><span class="sxs-lookup"><span data-stu-id="23e7d-102">Zip function</span></span>

<span data-ttu-id="23e7d-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="23e7d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="23e7d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23e7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="23e7d-105">Zip foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="23e7d-105">Zip has been deprecated.</span></span> <span data-ttu-id="23e7d-106">Por favor, use <xref:Microsoft.Quantum.Arrays.Zipped> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="23e7d-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="23e7d-107">Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="23e7d-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="23e7d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="23e7d-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="23e7d-109">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="23e7d-109">left : 'T[]</span></span>

<span data-ttu-id="23e7d-110">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="23e7d-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="23e7d-111">direito : 'U[]</span><span class="sxs-lookup"><span data-stu-id="23e7d-111">right : 'U[]</span></span>

<span data-ttu-id="23e7d-112">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="23e7d-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="23e7d-113">Saída : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="23e7d-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="23e7d-114">Uma matriz contendo pares da forma `(left[idx], right[idx])` para cada `idx` um .</span><span class="sxs-lookup"><span data-stu-id="23e7d-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="23e7d-115">Se as duas matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="23e7d-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23e7d-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="23e7d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23e7d-117">'T</span><span class="sxs-lookup"><span data-stu-id="23e7d-117">'T</span></span>

<span data-ttu-id="23e7d-118">O tipo de elementos da matriz esquerda.</span><span class="sxs-lookup"><span data-stu-id="23e7d-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="23e7d-119">'U</span><span class="sxs-lookup"><span data-stu-id="23e7d-119">'U</span></span>

<span data-ttu-id="23e7d-120">O tipo de elementos de matriz certos.</span><span class="sxs-lookup"><span data-stu-id="23e7d-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="23e7d-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="23e7d-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="23e7d-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="23e7d-122">See Also</span></span>

- [<span data-ttu-id="23e7d-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="23e7d-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="23e7d-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="23e7d-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="23e7d-125">Microsoft.Quantum.Arrays.Unzipped</span><span class="sxs-lookup"><span data-stu-id="23e7d-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)