---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Função dividida
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220506"
---
# <a name="partitioned-function"></a><span data-ttu-id="64144-102">Função dividida</span><span class="sxs-lookup"><span data-stu-id="64144-102">Partitioned function</span></span>

<span data-ttu-id="64144-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="64144-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="64144-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64144-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64144-105">Divide uma matriz em várias partes.</span><span class="sxs-lookup"><span data-stu-id="64144-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="64144-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="64144-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="64144-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="64144-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="64144-108">Número de elementos em cada parte da matriz</span><span class="sxs-lookup"><span data-stu-id="64144-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="64144-109">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="64144-109">arr : 'T[]</span></span>

<span data-ttu-id="64144-110">Matriz de entrada a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="64144-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="64144-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="64144-111">Output : 'T[][]</span></span>

<span data-ttu-id="64144-112">Múltiplas matrizes onde a primeira matriz é a primeira `nElements[0]` e a segunda matriz são as `arr` `nElements[1]` próximas `arr` etc. A última matriz conterá todos os elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="64144-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64144-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="64144-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64144-114">'T</span><span class="sxs-lookup"><span data-stu-id="64144-114">'T</span></span>

