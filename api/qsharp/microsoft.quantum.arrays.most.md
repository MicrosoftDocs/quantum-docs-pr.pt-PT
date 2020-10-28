---
uid: Microsoft.Quantum.Arrays.Most
title: A maioria da função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719002"
---
# <a name="most-function"></a><span data-ttu-id="35475-102">A maioria da função</span><span class="sxs-lookup"><span data-stu-id="35475-102">Most function</span></span>

<span data-ttu-id="35475-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35475-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35475-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35475-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35475-105">Cria uma matriz que é igual a uma matriz de entrada, exceto que o último elemento de matriz é largado.</span><span class="sxs-lookup"><span data-stu-id="35475-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="35475-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="35475-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="35475-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="35475-107">array : 'T[]</span></span>

<span data-ttu-id="35475-108">Uma matriz cujos primeiros e últimos elementos são para formar a matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="35475-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="35475-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="35475-109">Output : 'T[]</span></span>

<span data-ttu-id="35475-110">Uma matriz contendo os `array[0..Length(array) - 2]` elementos.</span><span class="sxs-lookup"><span data-stu-id="35475-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35475-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="35475-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35475-112">'T</span><span class="sxs-lookup"><span data-stu-id="35475-112">'T</span></span>

<span data-ttu-id="35475-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="35475-113">The type of the array elements.</span></span>