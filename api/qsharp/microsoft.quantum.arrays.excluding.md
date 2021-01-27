---
uid: Microsoft.Quantum.Arrays.Excluding
title: Excluindo a função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: c117431e3d98bba4ed3d29cb0b171247bf77be0b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848659"
---
# <a name="excluding-function"></a><span data-ttu-id="2765e-102">Excluindo a função</span><span class="sxs-lookup"><span data-stu-id="2765e-102">Excluding function</span></span>

<span data-ttu-id="2765e-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2765e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2765e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2765e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2765e-105">Devolve uma matriz contendo os elementos de outra matriz, excluindo elementos numa determinada lista de índices.</span><span class="sxs-lookup"><span data-stu-id="2765e-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2765e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2765e-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="2765e-107">remover: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2765e-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2765e-108">Um conjunto de índices que denotam quais os elementos que devem ser excluídos da saída.</span><span class="sxs-lookup"><span data-stu-id="2765e-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="2765e-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="2765e-109">array : 'T[]</span></span>

<span data-ttu-id="2765e-110">Matriz dos quais são tomados os valores na matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="2765e-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="2765e-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="2765e-111">Output : 'T[]</span></span>

<span data-ttu-id="2765e-112">Um conjunto `output` tal que é o primeiro elemento de cujo índice não aparece em , tal que `output[0]` é o segundo `array` `remove` `output[1]` elemento, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2765e-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2765e-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2765e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2765e-114">'T</span><span class="sxs-lookup"><span data-stu-id="2765e-114">'T</span></span>

<span data-ttu-id="2765e-115">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="2765e-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="2765e-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2765e-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Excluding([1, 3, 4], array);
```