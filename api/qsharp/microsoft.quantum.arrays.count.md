---
uid: Microsoft.Quantum.Arrays.Count
title: Função contagem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842839"
---
# <a name="count-function"></a><span data-ttu-id="9bba6-102">Função contagem</span><span class="sxs-lookup"><span data-stu-id="9bba6-102">Count function</span></span>

<span data-ttu-id="9bba6-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9bba6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9bba6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9bba6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9bba6-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, devolve o número de elementos uma matriz que consiste nos elementos que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="9bba6-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="9bba6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9bba6-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="9bba6-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9bba6-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9bba6-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="9bba6-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="9bba6-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="9bba6-109">array : 'T[]</span></span>

<span data-ttu-id="9bba6-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="9bba6-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="9bba6-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9bba6-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9bba6-112">O número de elementos `array` que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="9bba6-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9bba6-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9bba6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9bba6-114">'T</span><span class="sxs-lookup"><span data-stu-id="9bba6-114">'T</span></span>

<span data-ttu-id="9bba6-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="9bba6-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="9bba6-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9bba6-116">Example</span></span>

<span data-ttu-id="9bba6-117">O seguinte código demonstra a função "Count".</span><span class="sxs-lookup"><span data-stu-id="9bba6-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="9bba6-118">Um predicado é definido usando a @"microsoft.quantum.logical.greaterthani" função:</span><span class="sxs-lookup"><span data-stu-id="9bba6-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="9bba6-119">Observações</span><span class="sxs-lookup"><span data-stu-id="9bba6-119">Remarks</span></span>

<span data-ttu-id="9bba6-120">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e um predicado `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="9bba6-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>