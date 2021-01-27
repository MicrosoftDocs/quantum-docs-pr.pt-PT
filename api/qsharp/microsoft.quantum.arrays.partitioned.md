---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Função dividida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845549"
---
# <a name="partitioned-function"></a><span data-ttu-id="bab53-102">Função dividida</span><span class="sxs-lookup"><span data-stu-id="bab53-102">Partitioned function</span></span>

<span data-ttu-id="bab53-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bab53-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bab53-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bab53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bab53-105">Divide uma matriz em várias partes.</span><span class="sxs-lookup"><span data-stu-id="bab53-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="bab53-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bab53-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="bab53-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bab53-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bab53-108">Número de elementos em cada parte da matriz</span><span class="sxs-lookup"><span data-stu-id="bab53-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="bab53-109">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="bab53-109">arr : 'T[]</span></span>

<span data-ttu-id="bab53-110">Matriz de entrada a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="bab53-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="bab53-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="bab53-111">Output : 'T[][]</span></span>

<span data-ttu-id="bab53-112">Múltiplas matrizes onde a primeira matriz é a primeira `nElements[0]` e a segunda matriz são as `arr` `nElements[1]` próximas `arr` etc. A última matriz conterá todos os elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="bab53-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bab53-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bab53-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bab53-114">'T</span><span class="sxs-lookup"><span data-stu-id="bab53-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="bab53-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bab53-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```