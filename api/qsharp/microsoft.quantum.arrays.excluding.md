---
uid: Microsoft.Quantum.Arrays.Excluding
title: Excluindo a função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719278"
---
# <a name="excluding-function"></a><span data-ttu-id="334e9-102">Excluindo a função</span><span class="sxs-lookup"><span data-stu-id="334e9-102">Excluding function</span></span>

<span data-ttu-id="334e9-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="334e9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="334e9-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="334e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="334e9-105">Devolve uma matriz contendo os elementos de outra matriz, excluindo elementos numa determinada lista de índices.</span><span class="sxs-lookup"><span data-stu-id="334e9-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="334e9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="334e9-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="334e9-107">remover: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="334e9-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="334e9-108">Um conjunto de índices que denotam quais os elementos que devem ser excluídos da saída.</span><span class="sxs-lookup"><span data-stu-id="334e9-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="334e9-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="334e9-109">array : 'T[]</span></span>

<span data-ttu-id="334e9-110">Matriz dos quais são tomados os valores na matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="334e9-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="334e9-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="334e9-111">Output : 'T[]</span></span>

<span data-ttu-id="334e9-112">Um conjunto `output` tal que é o primeiro elemento de cujo índice não aparece em , tal que `output[0]` é o segundo `array` `remove` `output[1]` elemento, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="334e9-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="334e9-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="334e9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="334e9-114">'T</span><span class="sxs-lookup"><span data-stu-id="334e9-114">'T</span></span>

<span data-ttu-id="334e9-115">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="334e9-115">The type of the array elements.</span></span>