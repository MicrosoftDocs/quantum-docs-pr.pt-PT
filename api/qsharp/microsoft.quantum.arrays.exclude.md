---
uid: Microsoft.Quantum.Arrays.Exclude
title: Excluir função
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221356"
---
# <a name="exclude-function"></a><span data-ttu-id="2f645-102">Excluir função</span><span class="sxs-lookup"><span data-stu-id="2f645-102">Exclude function</span></span>

<span data-ttu-id="2f645-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f645-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f645-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f645-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f645-105">Devolve uma matriz contendo os elementos de outra matriz, excluindo elementos numa determinada lista de índices.</span><span class="sxs-lookup"><span data-stu-id="2f645-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2f645-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2f645-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="2f645-107">remover: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2f645-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2f645-108">Um conjunto de índices que denotam quais os elementos que devem ser excluídos da saída.</span><span class="sxs-lookup"><span data-stu-id="2f645-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="2f645-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="2f645-109">array : 'T[]</span></span>

<span data-ttu-id="2f645-110">Matriz dos quais são tomados os valores na matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="2f645-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="2f645-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="2f645-111">Output : 'T[]</span></span>

<span data-ttu-id="2f645-112">Um conjunto `output` tal que é o primeiro elemento de cujo índice não aparece em , tal que `output[0]` é o segundo `array` `remove` `output[1]` elemento, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2f645-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2f645-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2f645-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f645-114">'T</span><span class="sxs-lookup"><span data-stu-id="2f645-114">'T</span></span>

<span data-ttu-id="2f645-115">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="2f645-115">The type of the array elements.</span></span>