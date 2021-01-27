---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: Função MappedOverRange
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845640"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="eb646-102">Função MappedOverRange</span><span class="sxs-lookup"><span data-stu-id="eb646-102">MappedOverRange function</span></span>

<span data-ttu-id="eb646-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="eb646-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="eb646-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb646-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb646-105">Dado um intervalo e uma função que toma um inteiro como entrada, devolve uma nova matriz que consiste nas imagens dos valores de gama sob a função.</span><span class="sxs-lookup"><span data-stu-id="eb646-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="eb646-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="eb646-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="eb646-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span><span class="sxs-lookup"><span data-stu-id="eb646-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="eb646-108">Uma função disso `Int` `'T` é usada para mapear valores de alcance.</span><span class="sxs-lookup"><span data-stu-id="eb646-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="eb646-109">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="eb646-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="eb646-110">Uma série de inteiros.</span><span class="sxs-lookup"><span data-stu-id="eb646-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="eb646-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="eb646-111">Output : 'T[]</span></span>

<span data-ttu-id="eb646-112">Uma matriz `'T[]` de elementos que são mapeados pela `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="eb646-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="eb646-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="eb646-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb646-114">'T</span><span class="sxs-lookup"><span data-stu-id="eb646-114">'T</span></span>

<span data-ttu-id="eb646-115">O tipo de resultado da `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="eb646-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="eb646-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eb646-116">Example</span></span>

<span data-ttu-id="eb646-117">Este exemplo adiciona 1 a uma gama de números pares:</span><span class="sxs-lookup"><span data-stu-id="eb646-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="eb646-118">Observações</span><span class="sxs-lookup"><span data-stu-id="eb646-118">Remarks</span></span>

<span data-ttu-id="eb646-119">A função é definida para tipos genéricos, ou seja, sempre que temos uma função `mapper: Int -> 'T` podemos mapear os valores da gama e produzir uma matriz de tipo `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="eb646-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb646-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eb646-120">See Also</span></span>

- [<span data-ttu-id="eb646-121">Microsoft.Quantum.Arrays.Mapeado</span><span class="sxs-lookup"><span data-stu-id="eb646-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)