---
uid: Microsoft.Quantum.Arrays.Most
title: A maioria da função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845587"
---
# <a name="most-function"></a><span data-ttu-id="85eb3-102">A maioria da função</span><span class="sxs-lookup"><span data-stu-id="85eb3-102">Most function</span></span>

<span data-ttu-id="85eb3-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="85eb3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="85eb3-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85eb3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85eb3-105">Cria uma matriz que é igual a uma matriz de entrada, exceto que o último elemento de matriz é largado.</span><span class="sxs-lookup"><span data-stu-id="85eb3-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="85eb3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="85eb3-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="85eb3-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="85eb3-107">array : 'T[]</span></span>

<span data-ttu-id="85eb3-108">Uma matriz cujos primeiros e últimos elementos são para formar a matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="85eb3-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="85eb3-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="85eb3-109">Output : 'T[]</span></span>

<span data-ttu-id="85eb3-110">Uma matriz contendo os `array[0..Length(array) - 2]` elementos.</span><span class="sxs-lookup"><span data-stu-id="85eb3-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="85eb3-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="85eb3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85eb3-112">'T</span><span class="sxs-lookup"><span data-stu-id="85eb3-112">'T</span></span>

<span data-ttu-id="85eb3-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="85eb3-113">The type of the array elements.</span></span>