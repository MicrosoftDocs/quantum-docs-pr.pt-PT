---
uid: Microsoft.Quantum.Arrays.Sorted
title: Função ordenada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845450"
---
# <a name="sorted-function"></a><span data-ttu-id="d1bd9-102">Função ordenada</span><span class="sxs-lookup"><span data-stu-id="d1bd9-102">Sorted function</span></span>

<span data-ttu-id="d1bd9-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d1bd9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d1bd9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1bd9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1bd9-105">Dada uma matriz, devolve os elementos dessa matriz classificados por uma determinada função de comparação.</span><span class="sxs-lookup"><span data-stu-id="d1bd9-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d1bd9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1bd9-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="d1bd9-107">comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d1bd9-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d1bd9-108">Uma função que compara dois elementos tais que `a` são considerados inferiores ou iguais a `b` se for `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="d1bd9-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="d1bd9-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d1bd9-109">array : 'T[]</span></span>

<span data-ttu-id="d1bd9-110">A matriz a ser ordenada.</span><span class="sxs-lookup"><span data-stu-id="d1bd9-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="d1bd9-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="d1bd9-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1bd9-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d1bd9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1bd9-113">'T</span><span class="sxs-lookup"><span data-stu-id="d1bd9-113">'T</span></span>

<span data-ttu-id="d1bd9-114">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="d1bd9-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="d1bd9-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d1bd9-115">Example</span></span>

<span data-ttu-id="d1bd9-116">O seguinte corte ordena uma matriz de inteiros a ocorrer por ordem crescente:</span><span class="sxs-lookup"><span data-stu-id="d1bd9-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="d1bd9-117">Observações</span><span class="sxs-lookup"><span data-stu-id="d1bd9-117">Remarks</span></span>

<span data-ttu-id="d1bd9-118">A função `comparison` é assumida como transitiva, de tal forma que se `comparison(a, b)` e , `comparison(b, c)` `comparison(a, c)` então, é assumido.</span><span class="sxs-lookup"><span data-stu-id="d1bd9-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="d1bd9-119">Se esta propriedade não tiver, então a saída desta função pode estar incorreta.</span><span class="sxs-lookup"><span data-stu-id="d1bd9-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="d1bd9-120">Como esta é uma função, os resultados são completamente determináveis, mesmo quando dois elementos são considerados iguais `comparison` em; isto é, quando `comparison(a, b)` e são `comparison(b, a)` `true` ambos.</span><span class="sxs-lookup"><span data-stu-id="d1bd9-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="d1bd9-121">Em particular, o tipo desempenhado por esta função é garantido ser estável, de modo que se dois elementos `a` e `b` ocorrerem nessa ordem dentro `array` e forem considerados iguais em , `comparison` `a` então também aparecerá antes `b` na saída.</span><span class="sxs-lookup"><span data-stu-id="d1bd9-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="d1bd9-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1bd9-122">For example:</span></span>

```qsharp
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