---
uid: Microsoft.Quantum.Arrays.Zipped
title: Função com fecho
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219758"
---
# <a name="zipped-function"></a><span data-ttu-id="504dd-102">Função com fecho</span><span class="sxs-lookup"><span data-stu-id="504dd-102">Zipped function</span></span>

<span data-ttu-id="504dd-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="504dd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="504dd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="504dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="504dd-105">Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="504dd-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="504dd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="504dd-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="504dd-107">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="504dd-107">left : 'T[]</span></span>

<span data-ttu-id="504dd-108">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="504dd-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="504dd-109">direito : 'U[]</span><span class="sxs-lookup"><span data-stu-id="504dd-109">right : 'U[]</span></span>

<span data-ttu-id="504dd-110">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="504dd-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="504dd-111">Saída : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="504dd-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="504dd-112">Uma matriz contendo pares da forma `(left[idx], right[idx])` para cada `idx` um .</span><span class="sxs-lookup"><span data-stu-id="504dd-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="504dd-113">Se as duas matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="504dd-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="504dd-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="504dd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="504dd-115">'T</span><span class="sxs-lookup"><span data-stu-id="504dd-115">'T</span></span>

<span data-ttu-id="504dd-116">O tipo de elementos da matriz esquerda.</span><span class="sxs-lookup"><span data-stu-id="504dd-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="504dd-117">'U</span><span class="sxs-lookup"><span data-stu-id="504dd-117">'U</span></span>

<span data-ttu-id="504dd-118">O tipo de elementos de matriz certos.</span><span class="sxs-lookup"><span data-stu-id="504dd-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="504dd-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="504dd-119">See Also</span></span>

- [<span data-ttu-id="504dd-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="504dd-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="504dd-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="504dd-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="504dd-122">Microsoft.Quantum.Arrays.Unzipped</span><span class="sxs-lookup"><span data-stu-id="504dd-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)