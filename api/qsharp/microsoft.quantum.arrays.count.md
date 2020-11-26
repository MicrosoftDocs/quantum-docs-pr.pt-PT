---
uid: Microsoft.Quantum.Arrays.Count
title: Função contagem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221560"
---
# <a name="count-function"></a><span data-ttu-id="50c11-102">Função contagem</span><span class="sxs-lookup"><span data-stu-id="50c11-102">Count function</span></span>

<span data-ttu-id="50c11-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50c11-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50c11-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50c11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="50c11-105">Dada uma matriz e um predicado que é definido para os elementos da matriz, devolve o número de elementos uma matriz que consiste nos elementos que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="50c11-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="50c11-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="50c11-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="50c11-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="50c11-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="50c11-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="50c11-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="50c11-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="50c11-109">array : 'T[]</span></span>

<span data-ttu-id="50c11-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="50c11-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="50c11-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50c11-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50c11-112">O número de elementos `array` que satisfazem o predicado.</span><span class="sxs-lookup"><span data-stu-id="50c11-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50c11-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="50c11-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50c11-114">'T</span><span class="sxs-lookup"><span data-stu-id="50c11-114">'T</span></span>

<span data-ttu-id="50c11-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="50c11-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="50c11-116">Observações</span><span class="sxs-lookup"><span data-stu-id="50c11-116">Remarks</span></span>

<span data-ttu-id="50c11-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e um predicado `'T -> Bool` podemos filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="50c11-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>