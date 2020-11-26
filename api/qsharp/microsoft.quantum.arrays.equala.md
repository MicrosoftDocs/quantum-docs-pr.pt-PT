---
uid: Microsoft.Quantum.Arrays.EqualA
title: Função EqualA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 176e15139a27d375fb047c07fa1ee778dc8cc2ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221373"
---
# <a name="equala-function"></a><span data-ttu-id="98b92-102">Função EqualA</span><span class="sxs-lookup"><span data-stu-id="98b92-102">EqualA function</span></span>

<span data-ttu-id="98b92-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="98b92-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="98b92-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98b92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98b92-105">Tendo em conta duas matrizes do mesmo tipo e um predicado que é definido para pares de elementos das matrizes, verifica se as matrizes são iguais.</span><span class="sxs-lookup"><span data-stu-id="98b92-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="98b92-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="98b92-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="98b92-107">igual: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="98b92-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="98b92-108">Uma função de tuple `('T, 'T)` para que é usada para verificar se dois `Bool` elementos de matrizes são iguais.</span><span class="sxs-lookup"><span data-stu-id="98b92-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="98b92-109">array1 : 'T[]</span><span class="sxs-lookup"><span data-stu-id="98b92-109">array1 : 'T[]</span></span>

<span data-ttu-id="98b92-110">A primeira matriz a ser comparada.</span><span class="sxs-lookup"><span data-stu-id="98b92-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="98b92-111">array2 : 'T[]</span><span class="sxs-lookup"><span data-stu-id="98b92-111">array2 : 'T[]</span></span>

<span data-ttu-id="98b92-112">A segunda matriz a ser comparada.</span><span class="sxs-lookup"><span data-stu-id="98b92-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="98b92-113">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="98b92-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="98b92-114">O valor `true` se e só se e é `array1` `array2` igual.</span><span class="sxs-lookup"><span data-stu-id="98b92-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="98b92-115">Isto é, se ambas as matrizes tiverem o mesmo comprimento, e todos os elementos forem iguais como definido por `equal` .</span><span class="sxs-lookup"><span data-stu-id="98b92-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="98b92-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="98b92-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98b92-117">'T</span><span class="sxs-lookup"><span data-stu-id="98b92-117">'T</span></span>

<span data-ttu-id="98b92-118">O tipo de elementos de cada matriz.</span><span class="sxs-lookup"><span data-stu-id="98b92-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="98b92-119">Observações</span><span class="sxs-lookup"><span data-stu-id="98b92-119">Remarks</span></span>

<span data-ttu-id="98b92-120">Esta função é definida para tipos genéricos; ou seja, sempre que temos duas matrizes `'T[]` e uma `equal: ('T, 'T) -> Bool` função, esta função devolve um valor `Bool` que indica se as matrizes são iguais.</span><span class="sxs-lookup"><span data-stu-id="98b92-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="98b92-121">Para que duas matrizes sejam consideradas iguais, têm de ter o mesmo comprimento e os elementos nas mesmas posições nas matrizes têm de ser iguais.</span><span class="sxs-lookup"><span data-stu-id="98b92-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>