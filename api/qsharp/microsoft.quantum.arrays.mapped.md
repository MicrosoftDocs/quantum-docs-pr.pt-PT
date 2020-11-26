---
uid: Microsoft.Quantum.Arrays.Mapped
title: Função mapeada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220744"
---
# <a name="mapped-function"></a><span data-ttu-id="0d521-102">Função mapeada</span><span class="sxs-lookup"><span data-stu-id="0d521-102">Mapped function</span></span>

<span data-ttu-id="0d521-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0d521-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0d521-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d521-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d521-105">Dada uma matriz e uma função que é definida para os elementos da matriz, devolve uma nova matriz que consiste nas imagens da matriz original sob a função.</span><span class="sxs-lookup"><span data-stu-id="0d521-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="0d521-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d521-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="0d521-107">mapper : 'T-> 'U</span><span class="sxs-lookup"><span data-stu-id="0d521-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="0d521-108">Uma função disso `'T` `'U` é usada para mapear elementos.</span><span class="sxs-lookup"><span data-stu-id="0d521-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="0d521-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="0d521-109">array : 'T[]</span></span>

<span data-ttu-id="0d521-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="0d521-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="0d521-111">Saída : 'U].</span><span class="sxs-lookup"><span data-stu-id="0d521-111">Output : 'U[]</span></span>

<span data-ttu-id="0d521-112">Uma matriz `'U[]` de elementos que são mapeados pela `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="0d521-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0d521-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0d521-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d521-114">'T</span><span class="sxs-lookup"><span data-stu-id="0d521-114">'T</span></span>

<span data-ttu-id="0d521-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="0d521-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="0d521-116">'U</span><span class="sxs-lookup"><span data-stu-id="0d521-116">'U</span></span>

<span data-ttu-id="0d521-117">O tipo de resultado da `mapper` função.</span><span class="sxs-lookup"><span data-stu-id="0d521-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d521-118">Observações</span><span class="sxs-lookup"><span data-stu-id="0d521-118">Remarks</span></span>

<span data-ttu-id="0d521-119">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `mapper: 'T -> 'U` podemos mapear os elementos da matriz e produzir uma nova matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="0d521-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>