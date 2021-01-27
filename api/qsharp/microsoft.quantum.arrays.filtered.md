---
uid: Microsoft.Quantum.Arrays.Filtered
title: Função filtrada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847165"
---
# <a name="filtered-function"></a><span data-ttu-id="bc7e7-102">Função filtrada</span><span class="sxs-lookup"><span data-stu-id="bc7e7-102">Filtered function</span></span>

<span data-ttu-id="bc7e7-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bc7e7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bc7e7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc7e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc7e7-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, devolve uma matriz que consiste nos elementos que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="bc7e7-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bc7e7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bc7e7-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="bc7e7-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bc7e7-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bc7e7-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="bc7e7-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="bc7e7-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="bc7e7-109">array : 'T[]</span></span>

<span data-ttu-id="bc7e7-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="bc7e7-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="bc7e7-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="bc7e7-111">Output : 'T[]</span></span>

<span data-ttu-id="bc7e7-112">Uma variedade `'T[]` de elementos que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="bc7e7-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bc7e7-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bc7e7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc7e7-114">'T</span><span class="sxs-lookup"><span data-stu-id="bc7e7-114">'T</span></span>

<span data-ttu-id="bc7e7-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="bc7e7-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="bc7e7-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bc7e7-116">Example</span></span>

<span data-ttu-id="bc7e7-117">O seguinte código demonstra a função "Filtrado".</span><span class="sxs-lookup"><span data-stu-id="bc7e7-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="bc7e7-118">Um predicado é definido usando a @"microsoft.quantum.logical.greaterthani" função:</span><span class="sxs-lookup"><span data-stu-id="bc7e7-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="bc7e7-119">O resultado que se deve esperar deste exemplo será um conjunto de números superiores a 5.</span><span class="sxs-lookup"><span data-stu-id="bc7e7-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc7e7-120">Observações</span><span class="sxs-lookup"><span data-stu-id="bc7e7-120">Remarks</span></span>

<span data-ttu-id="bc7e7-121">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e um predicado `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="bc7e7-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>