---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Função dividida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718978"
---
# <a name="partitioned-function"></a><span data-ttu-id="2fb5c-102">Função dividida</span><span class="sxs-lookup"><span data-stu-id="2fb5c-102">Partitioned function</span></span>

<span data-ttu-id="2fb5c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2fb5c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2fb5c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fb5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fb5c-105">Divide uma matriz em várias partes.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="2fb5c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2fb5c-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="2fb5c-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2fb5c-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2fb5c-108">Número de elementos em cada parte da matriz</span><span class="sxs-lookup"><span data-stu-id="2fb5c-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="2fb5c-109">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="2fb5c-109">arr : 'T[]</span></span>

<span data-ttu-id="2fb5c-110">Matriz de entrada a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="2fb5c-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="2fb5c-111">Output : 'T[][]</span></span>

<span data-ttu-id="2fb5c-112">Múltiplas matrizes onde a primeira matriz é a primeira `nElements[0]` e a segunda matriz são as `arr` `nElements[1]` próximas `arr` etc. A última matriz conterá todos os elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2fb5c-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2fb5c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2fb5c-114">'T</span><span class="sxs-lookup"><span data-stu-id="2fb5c-114">'T</span></span>

