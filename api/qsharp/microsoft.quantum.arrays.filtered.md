---
uid: Microsoft.Quantum.Arrays.Filtered
title: Função filtrada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: fa8600f4d773daf6eabf8b9961ab46961155d1fd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221271"
---
# <a name="filtered-function"></a><span data-ttu-id="d72d9-102">Função filtrada</span><span class="sxs-lookup"><span data-stu-id="d72d9-102">Filtered function</span></span>

<span data-ttu-id="d72d9-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d72d9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d72d9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d72d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d72d9-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, devolve uma matriz que consiste nos elementos que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="d72d9-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d72d9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d72d9-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="d72d9-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d72d9-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d72d9-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="d72d9-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="d72d9-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d72d9-109">array : 'T[]</span></span>

<span data-ttu-id="d72d9-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="d72d9-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="d72d9-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="d72d9-111">Output : 'T[]</span></span>

<span data-ttu-id="d72d9-112">Uma variedade `'T[]` de elementos que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="d72d9-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d72d9-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d72d9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d72d9-114">'T</span><span class="sxs-lookup"><span data-stu-id="d72d9-114">'T</span></span>

<span data-ttu-id="d72d9-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="d72d9-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="d72d9-116">Observações</span><span class="sxs-lookup"><span data-stu-id="d72d9-116">Remarks</span></span>

<span data-ttu-id="d72d9-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e um predicado `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="d72d9-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>