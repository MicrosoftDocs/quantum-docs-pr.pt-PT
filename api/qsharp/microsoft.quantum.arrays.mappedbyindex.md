---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Função MapedByIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719051"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="c72cb-102">Função MapedByIndex</span><span class="sxs-lookup"><span data-stu-id="c72cb-102">MappedByIndex function</span></span>

<span data-ttu-id="c72cb-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c72cb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c72cb-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c72cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c72cb-105">Dada uma matriz e uma função que é definida para os elementos indexados da matriz, devolve uma nova matriz que consiste nas imagens da matriz original sob a função.</span><span class="sxs-lookup"><span data-stu-id="c72cb-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c72cb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c72cb-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="c72cb-107">mapper :[(Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span><span class="sxs-lookup"><span data-stu-id="c72cb-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="c72cb-108">Uma função disso `(Int, 'T)` `'U` é usada para mapear elementos e seus índices.</span><span class="sxs-lookup"><span data-stu-id="c72cb-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="c72cb-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="c72cb-109">array : 'T[]</span></span>

<span data-ttu-id="c72cb-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="c72cb-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c72cb-111">Saída : 'U].</span><span class="sxs-lookup"><span data-stu-id="c72cb-111">Output : 'U[]</span></span>

<span data-ttu-id="c72cb-112">Uma matriz `'U[]` de elementos que são mapeados pela `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="c72cb-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c72cb-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c72cb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c72cb-114">'T</span><span class="sxs-lookup"><span data-stu-id="c72cb-114">'T</span></span>

<span data-ttu-id="c72cb-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="c72cb-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c72cb-116">'U</span><span class="sxs-lookup"><span data-stu-id="c72cb-116">'U</span></span>

<span data-ttu-id="c72cb-117">O tipo de resultado da `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="c72cb-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c72cb-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c72cb-118">See Also</span></span>

- [<span data-ttu-id="c72cb-119">Microsoft.Quantum.Arrays.Mapeado</span><span class="sxs-lookup"><span data-stu-id="c72cb-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)