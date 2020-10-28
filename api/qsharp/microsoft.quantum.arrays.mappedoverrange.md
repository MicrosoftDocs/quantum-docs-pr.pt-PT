---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Função MappedOverRange
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719039"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="20453-102">Função MappedOverRange</span><span class="sxs-lookup"><span data-stu-id="20453-102">MappedOverRange function</span></span>

<span data-ttu-id="20453-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="20453-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="20453-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20453-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20453-105">Dado um intervalo e uma função que toma um inteiro como entrada, devolve uma nova matriz que consiste nas imagens dos valores de gama sob a função.</span><span class="sxs-lookup"><span data-stu-id="20453-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="20453-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="20453-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="20453-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span><span class="sxs-lookup"><span data-stu-id="20453-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="20453-108">Uma função disso `Int` `'T` é usada para mapear valores de alcance.</span><span class="sxs-lookup"><span data-stu-id="20453-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="20453-109">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="20453-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="20453-110">Uma série de inteiros.</span><span class="sxs-lookup"><span data-stu-id="20453-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="20453-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="20453-111">Output : 'T[]</span></span>

<span data-ttu-id="20453-112">Uma matriz `'T[]` de elementos que são mapeados pela `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="20453-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20453-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="20453-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20453-114">'T</span><span class="sxs-lookup"><span data-stu-id="20453-114">'T</span></span>

<span data-ttu-id="20453-115">O tipo de resultado da `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="20453-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="20453-116">Observações</span><span class="sxs-lookup"><span data-stu-id="20453-116">Remarks</span></span>

<span data-ttu-id="20453-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma função `mapper: Int -> 'T` podemos mapear os valores da gama e produzir uma matriz de tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="20453-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="20453-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="20453-118">See Also</span></span>

- [<span data-ttu-id="20453-119">Microsoft.Quantum.Arrays.Mapeado</span><span class="sxs-lookup"><span data-stu-id="20453-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)