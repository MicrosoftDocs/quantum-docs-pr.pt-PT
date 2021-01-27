---
uid: Microsoft.Quantum.Arrays.All
title: Todas as funções
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842887"
---
# <a name="all-function"></a><span data-ttu-id="f1066-102">Todas as funções</span><span class="sxs-lookup"><span data-stu-id="f1066-102">All function</span></span>

<span data-ttu-id="f1066-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f1066-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f1066-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1066-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1066-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, e verifica se todos os elementos da matriz satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="f1066-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="f1066-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f1066-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="f1066-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f1066-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f1066-108">Uma função a partir `'T` do que é usada para verificar `Bool` elementos.</span><span class="sxs-lookup"><span data-stu-id="f1066-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="f1066-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f1066-109">array : 'T[]</span></span>

<span data-ttu-id="f1066-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="f1066-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f1066-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f1066-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f1066-112">Um `Bool` valor da função E do predicado aplicado a todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="f1066-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f1066-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f1066-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1066-114">'T</span><span class="sxs-lookup"><span data-stu-id="f1066-114">'T</span></span>

<span data-ttu-id="f1066-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="f1066-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="f1066-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f1066-116">Example</span></span>

<span data-ttu-id="f1066-117">O código seguinte verifica se todos os elementos da matriz não são zero:</span><span class="sxs-lookup"><span data-stu-id="f1066-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="f1066-118">Observações</span><span class="sxs-lookup"><span data-stu-id="f1066-118">Remarks</span></span>

<span data-ttu-id="f1066-119">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `predicate: 'T -> Bool` podemos produzir um valor que indique `Bool` se todos os elementos satisfazem `predicate` .</span><span class="sxs-lookup"><span data-stu-id="f1066-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>