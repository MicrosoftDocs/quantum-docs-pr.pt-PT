---
uid: Microsoft.Quantum.Arrays.All
title: Todas as funções
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719482"
---
# <a name="all-function"></a><span data-ttu-id="16c63-102">Todas as funções</span><span class="sxs-lookup"><span data-stu-id="16c63-102">All function</span></span>

<span data-ttu-id="16c63-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="16c63-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="16c63-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16c63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16c63-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, e verifica se todos os elementos da matriz satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="16c63-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="16c63-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="16c63-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="16c63-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16c63-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="16c63-108">Uma função a partir `'T` do que é usada para verificar `Bool` elementos.</span><span class="sxs-lookup"><span data-stu-id="16c63-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="16c63-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="16c63-109">array : 'T[]</span></span>

<span data-ttu-id="16c63-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="16c63-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="16c63-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16c63-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="16c63-112">Um `Bool` valor da função E do predicado aplicado a todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="16c63-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="16c63-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="16c63-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16c63-114">'T</span><span class="sxs-lookup"><span data-stu-id="16c63-114">'T</span></span>

<span data-ttu-id="16c63-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="16c63-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="16c63-116">Observações</span><span class="sxs-lookup"><span data-stu-id="16c63-116">Remarks</span></span>

<span data-ttu-id="16c63-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `predicate: 'T -> Bool` podemos produzir um valor que indique `Bool` se todos os elementos satisfazem `predicate` .</span><span class="sxs-lookup"><span data-stu-id="16c63-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>