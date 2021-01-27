---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Função MapedByIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845670"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="b845d-102">Função MapedByIndex</span><span class="sxs-lookup"><span data-stu-id="b845d-102">MappedByIndex function</span></span>

<span data-ttu-id="b845d-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b845d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b845d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b845d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b845d-105">Dada uma matriz e uma função que é definida para os elementos indexados da matriz, devolve uma nova matriz que consiste nas imagens da matriz original sob a função.</span><span class="sxs-lookup"><span data-stu-id="b845d-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="b845d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b845d-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="b845d-107">mapper :[(Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span><span class="sxs-lookup"><span data-stu-id="b845d-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="b845d-108">Uma função disso `(Int, 'T)` `'U` é usada para mapear elementos e seus índices.</span><span class="sxs-lookup"><span data-stu-id="b845d-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="b845d-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="b845d-109">array : 'T[]</span></span>

<span data-ttu-id="b845d-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="b845d-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="b845d-111">Saída : 'U].</span><span class="sxs-lookup"><span data-stu-id="b845d-111">Output : 'U[]</span></span>

<span data-ttu-id="b845d-112">Uma matriz `'U[]` de elementos que são mapeados pela `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="b845d-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b845d-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b845d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b845d-114">'T</span><span class="sxs-lookup"><span data-stu-id="b845d-114">'T</span></span>

<span data-ttu-id="b845d-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="b845d-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="b845d-116">'U</span><span class="sxs-lookup"><span data-stu-id="b845d-116">'U</span></span>

<span data-ttu-id="b845d-117">O tipo de resultado da `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="b845d-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="b845d-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b845d-118">Example</span></span>

<span data-ttu-id="b845d-119">As duas linhas seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="b845d-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="b845d-120">e</span><span class="sxs-lookup"><span data-stu-id="b845d-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="b845d-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b845d-121">See Also</span></span>

- [<span data-ttu-id="b845d-122">Microsoft.Quantum.Arrays.Mapeado</span><span class="sxs-lookup"><span data-stu-id="b845d-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)