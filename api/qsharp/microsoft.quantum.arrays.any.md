---
uid: Microsoft.Quantum.Arrays.Any
title: Qualquer função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719471"
---
# <a name="any-function"></a><span data-ttu-id="35209-102">Qualquer função</span><span class="sxs-lookup"><span data-stu-id="35209-102">Any function</span></span>

<span data-ttu-id="35209-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35209-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35209-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35209-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35209-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, verifica se pelo menos um elemento da matriz satisfaz o predicado.</span><span class="sxs-lookup"><span data-stu-id="35209-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="35209-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="35209-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="35209-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="35209-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35209-108">Uma função a partir `'T` do que é usada para verificar `Bool` elementos.</span><span class="sxs-lookup"><span data-stu-id="35209-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="35209-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="35209-109">array : 'T[]</span></span>

<span data-ttu-id="35209-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="35209-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="35209-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="35209-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35209-112">Um `Bool` valor da função OR do predicado aplicado a todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="35209-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35209-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="35209-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35209-114">'T</span><span class="sxs-lookup"><span data-stu-id="35209-114">'T</span></span>

<span data-ttu-id="35209-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="35209-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="35209-116">Observações</span><span class="sxs-lookup"><span data-stu-id="35209-116">Remarks</span></span>

<span data-ttu-id="35209-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `predicate: 'T -> Bool` podemos produzir um valor que indica `Bool` se algum elemento satisfaz `predicate` .</span><span class="sxs-lookup"><span data-stu-id="35209-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>