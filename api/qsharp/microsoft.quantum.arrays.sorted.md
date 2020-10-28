---
uid: Microsoft.Quantum.Arrays.Sorted
title: Função ordenada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718883"
---
# <a name="sorted-function"></a><span data-ttu-id="effd2-102">Função ordenada</span><span class="sxs-lookup"><span data-stu-id="effd2-102">Sorted function</span></span>

<span data-ttu-id="effd2-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="effd2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="effd2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="effd2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="effd2-105">Dada uma matriz, devolve os elementos dessa matriz classificados por uma determinada função de comparação.</span><span class="sxs-lookup"><span data-stu-id="effd2-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="effd2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="effd2-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="effd2-107">comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="effd2-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="effd2-108">Uma função que compara dois elementos tais que `a` são considerados inferiores ou iguais a `b` se for `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="effd2-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="effd2-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="effd2-109">array : 'T[]</span></span>

<span data-ttu-id="effd2-110">A matriz a ser ordenada.</span><span class="sxs-lookup"><span data-stu-id="effd2-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="effd2-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="effd2-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="effd2-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="effd2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="effd2-113">'T</span><span class="sxs-lookup"><span data-stu-id="effd2-113">'T</span></span>

<span data-ttu-id="effd2-114">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="effd2-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="effd2-115">Observações</span><span class="sxs-lookup"><span data-stu-id="effd2-115">Remarks</span></span>

<span data-ttu-id="effd2-116">A função `comparison` é assumida como transitiva, de tal forma que se `comparison(a, b)` e , `comparison(b, c)` `comparison(a, c)` então, é assumido.</span><span class="sxs-lookup"><span data-stu-id="effd2-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="effd2-117">Se esta propriedade não tiver, então a saída desta função pode estar incorreta.</span><span class="sxs-lookup"><span data-stu-id="effd2-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="effd2-118">Como esta é uma função, os resultados são completamente determináveis, mesmo quando dois elementos são considerados iguais `comparison` em; isto é, quando `comparison(a, b)` e são `comparison(b, a)` `true` ambos.</span><span class="sxs-lookup"><span data-stu-id="effd2-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="effd2-119">Em particular, o tipo desempenhado por esta função é garantido ser estável, de modo que se dois elementos `a` e `b` ocorrerem nessa ordem dentro `array` e forem considerados iguais em , `comparison` `a` então também aparecerá antes `b` na saída.</span><span class="sxs-lookup"><span data-stu-id="effd2-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="effd2-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="effd2-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```