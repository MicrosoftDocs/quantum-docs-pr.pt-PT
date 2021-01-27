---
uid: Microsoft.Quantum.Arrays.Any
title: Qualquer função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846271"
---
# <a name="any-function"></a><span data-ttu-id="8b862-102">Qualquer função</span><span class="sxs-lookup"><span data-stu-id="8b862-102">Any function</span></span>

<span data-ttu-id="8b862-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b862-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b862-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b862-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b862-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, verifica se pelo menos um elemento da matriz satisfaz o predicado.</span><span class="sxs-lookup"><span data-stu-id="8b862-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="8b862-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b862-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8b862-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b862-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b862-108">Uma função a partir `'T` do que é usada para verificar `Bool` elementos.</span><span class="sxs-lookup"><span data-stu-id="8b862-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="8b862-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="8b862-109">array : 'T[]</span></span>

<span data-ttu-id="8b862-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="8b862-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8b862-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b862-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b862-112">Um `Bool` valor da função OR do predicado aplicado a todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="8b862-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b862-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8b862-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b862-114">'T</span><span class="sxs-lookup"><span data-stu-id="8b862-114">'T</span></span>

<span data-ttu-id="8b862-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="8b862-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="8b862-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8b862-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="8b862-117">Observações</span><span class="sxs-lookup"><span data-stu-id="8b862-117">Remarks</span></span>

<span data-ttu-id="8b862-118">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `predicate: 'T -> Bool` podemos produzir um valor que indica `Bool` se algum elemento satisfaz `predicate` .</span><span class="sxs-lookup"><span data-stu-id="8b862-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>