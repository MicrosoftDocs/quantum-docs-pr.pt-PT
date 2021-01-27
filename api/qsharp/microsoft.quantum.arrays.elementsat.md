---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementosAt função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 295aa4e2d79857405186b835d9788f59db83d1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842801"
---
# <a name="elementsat-function"></a><span data-ttu-id="274d4-102">ElementosAt função</span><span class="sxs-lookup"><span data-stu-id="274d4-102">ElementsAt function</span></span>

<span data-ttu-id="274d4-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="274d4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="274d4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="274d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="274d4-105">Devolve os elementos da matriz a uma dada gama de índices.</span><span class="sxs-lookup"><span data-stu-id="274d4-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="274d4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="274d4-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="274d4-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="274d4-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="274d4-108">Gama de índices de matriz</span><span class="sxs-lookup"><span data-stu-id="274d4-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="274d4-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="274d4-109">array : 'T[]</span></span>

<span data-ttu-id="274d4-110">Matriz</span><span class="sxs-lookup"><span data-stu-id="274d4-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="274d4-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="274d4-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="274d4-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="274d4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="274d4-113">'T</span><span class="sxs-lookup"><span data-stu-id="274d4-113">'T</span></span>

<span data-ttu-id="274d4-114">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="274d4-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="274d4-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="274d4-115">Example</span></span>

<span data-ttu-id="274d4-116">Obtenha os índices ímpares em sequências de inteiros famosos.</span><span class="sxs-lookup"><span data-stu-id="274d4-116">Get the odd indexes in famous integer sequences.</span></span> <span data-ttu-id="274d4-117">(note que o índice 0 corresponde ao _primeiro_ valor da sequência.)</span><span class="sxs-lookup"><span data-stu-id="274d4-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famousOdd = Mapped(ElementsAt<Int>(0..2..9, _), [lucas, prime, fibonacci, catalan]);
// same as: famousOdd = [[2, 3, 7, 18, 47], [2, 5, 11, 17, 23], [0, 1, 3, 8, 21], [1, 2, 14, 132, 1430]]
```

## <a name="see-also"></a><span data-ttu-id="274d4-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="274d4-118">See Also</span></span>

- [<span data-ttu-id="274d4-119">Microsoft.Quantum.Arrays.ElementAt</span><span class="sxs-lookup"><span data-stu-id="274d4-119">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="274d4-120">Microsoft.Quantum.Arrays.LookupFunction</span><span class="sxs-lookup"><span data-stu-id="274d4-120">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)