---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Função MappedOverRange
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220693"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="39dec-102">Função MappedOverRange</span><span class="sxs-lookup"><span data-stu-id="39dec-102">MappedOverRange function</span></span>

<span data-ttu-id="39dec-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39dec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39dec-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39dec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39dec-105">Dado um intervalo e uma função que toma um inteiro como entrada, devolve uma nova matriz que consiste nas imagens dos valores de gama sob a função.</span><span class="sxs-lookup"><span data-stu-id="39dec-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="39dec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="39dec-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="39dec-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span><span class="sxs-lookup"><span data-stu-id="39dec-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="39dec-108">Uma função disso `Int` `'T` é usada para mapear valores de alcance.</span><span class="sxs-lookup"><span data-stu-id="39dec-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="39dec-109">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="39dec-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="39dec-110">Uma série de inteiros.</span><span class="sxs-lookup"><span data-stu-id="39dec-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="39dec-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="39dec-111">Output : 'T[]</span></span>

<span data-ttu-id="39dec-112">Uma matriz `'T[]` de elementos que são mapeados pela `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="39dec-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39dec-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="39dec-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39dec-114">'T</span><span class="sxs-lookup"><span data-stu-id="39dec-114">'T</span></span>

<span data-ttu-id="39dec-115">O tipo de resultado da `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="39dec-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="39dec-116">Observações</span><span class="sxs-lookup"><span data-stu-id="39dec-116">Remarks</span></span>

<span data-ttu-id="39dec-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma função `mapper: Int -> 'T` podemos mapear os valores da gama e produzir uma matriz de tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="39dec-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="39dec-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="39dec-118">See Also</span></span>

- [<span data-ttu-id="39dec-119">Microsoft.Quantum.Arrays.Mapeado</span><span class="sxs-lookup"><span data-stu-id="39dec-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)