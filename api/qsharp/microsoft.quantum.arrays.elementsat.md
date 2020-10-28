---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementosAt função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: b4bbba4dc83c4f9b89cdcb8ec32769f1c586357e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719339"
---
# <a name="elementsat-function"></a><span data-ttu-id="a24db-102">ElementosAt função</span><span class="sxs-lookup"><span data-stu-id="a24db-102">ElementsAt function</span></span>

<span data-ttu-id="a24db-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a24db-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a24db-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a24db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a24db-105">Devolve os elementos da matriz a uma dada gama de índices.</span><span class="sxs-lookup"><span data-stu-id="a24db-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a24db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a24db-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="a24db-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a24db-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a24db-108">Gama de índices de matriz</span><span class="sxs-lookup"><span data-stu-id="a24db-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="a24db-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="a24db-109">array : 'T[]</span></span>

<span data-ttu-id="a24db-110">Matriz</span><span class="sxs-lookup"><span data-stu-id="a24db-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="a24db-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="a24db-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a24db-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a24db-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a24db-113">'T</span><span class="sxs-lookup"><span data-stu-id="a24db-113">'T</span></span>

<span data-ttu-id="a24db-114">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="a24db-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a24db-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a24db-115">See Also</span></span>

- [<span data-ttu-id="a24db-116">Microsoft.Quantum.Arrays.ElementAt</span><span class="sxs-lookup"><span data-stu-id="a24db-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="a24db-117">Microsoft.Quantum.Arrays.LookupFunction</span><span class="sxs-lookup"><span data-stu-id="a24db-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)