---
uid: Microsoft.Quantum.Arrays.Zipped
title: Função com fecho
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718714"
---
# <a name="zipped-function"></a><span data-ttu-id="d93ac-102">Função com fecho</span><span class="sxs-lookup"><span data-stu-id="d93ac-102">Zipped function</span></span>

<span data-ttu-id="d93ac-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d93ac-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d93ac-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d93ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d93ac-105">Tendo em conta duas matrizes, devolve uma nova matriz de pares de tal forma que cada par contém um elemento de cada matriz original.</span><span class="sxs-lookup"><span data-stu-id="d93ac-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="d93ac-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d93ac-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="d93ac-107">esquerda : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d93ac-107">left : 'T[]</span></span>

<span data-ttu-id="d93ac-108">Uma matriz contendo valores para o primeiro elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="d93ac-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="d93ac-109">direito : 'U[]</span><span class="sxs-lookup"><span data-stu-id="d93ac-109">right : 'U[]</span></span>

<span data-ttu-id="d93ac-110">Uma matriz contendo valores para o segundo elemento de cada tuple.</span><span class="sxs-lookup"><span data-stu-id="d93ac-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="d93ac-111">Saída : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="d93ac-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="d93ac-112">Uma matriz contendo pares da forma `(left[idx], right[idx])` para cada `idx` um .</span><span class="sxs-lookup"><span data-stu-id="d93ac-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="d93ac-113">Se as duas matrizes não tão longas, a saída será tão curta quanto a mais curta das entradas.</span><span class="sxs-lookup"><span data-stu-id="d93ac-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d93ac-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d93ac-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d93ac-115">'T</span><span class="sxs-lookup"><span data-stu-id="d93ac-115">'T</span></span>

<span data-ttu-id="d93ac-116">O tipo de elementos da matriz esquerda.</span><span class="sxs-lookup"><span data-stu-id="d93ac-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="d93ac-117">'U</span><span class="sxs-lookup"><span data-stu-id="d93ac-117">'U</span></span>

<span data-ttu-id="d93ac-118">O tipo de elementos de matriz certos.</span><span class="sxs-lookup"><span data-stu-id="d93ac-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="d93ac-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d93ac-119">See Also</span></span>

- [<span data-ttu-id="d93ac-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="d93ac-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="d93ac-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="d93ac-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="d93ac-122">Microsoft.Quantum.Arrays.Unzipped</span><span class="sxs-lookup"><span data-stu-id="d93ac-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)