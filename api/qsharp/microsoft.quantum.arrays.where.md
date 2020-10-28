---
uid: Microsoft.Quantum.Arrays.Where
title: Onde funciona
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718751"
---
# <a name="where-function"></a><span data-ttu-id="4a7dd-102">Onde funciona</span><span class="sxs-lookup"><span data-stu-id="4a7dd-102">Where function</span></span>

<span data-ttu-id="4a7dd-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a7dd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a7dd-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a7dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a7dd-105">Dado um predicado e uma matriz, devolve os índices daquela matriz onde o predicado é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4a7dd-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="4a7dd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4a7dd-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="4a7dd-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4a7dd-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4a7dd-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="4a7dd-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="4a7dd-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4a7dd-109">array : 'T[]</span></span>

<span data-ttu-id="4a7dd-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="4a7dd-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="4a7dd-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4a7dd-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4a7dd-112">Uma série de índices onde `predicate` é verdade.</span><span class="sxs-lookup"><span data-stu-id="4a7dd-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4a7dd-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4a7dd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a7dd-114">'T</span><span class="sxs-lookup"><span data-stu-id="4a7dd-114">'T</span></span>

<span data-ttu-id="4a7dd-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="4a7dd-115">The type of `array` elements.</span></span>