---
uid: Microsoft.Quantum.Arrays.Rest
title: Função de repouso
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220401"
---
# <a name="rest-function"></a><span data-ttu-id="2152c-102">Função de repouso</span><span class="sxs-lookup"><span data-stu-id="2152c-102">Rest function</span></span>

<span data-ttu-id="2152c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2152c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2152c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2152c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2152c-105">Cria uma matriz que é igual a uma matriz de entrada, exceto que o primeiro elemento de matriz é largado.</span><span class="sxs-lookup"><span data-stu-id="2152c-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2152c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2152c-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="2152c-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="2152c-107">array : 'T[]</span></span>

<span data-ttu-id="2152c-108">Uma matriz cujos segundos e últimos elementos são para formar a matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="2152c-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2152c-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="2152c-109">Output : 'T[]</span></span>

<span data-ttu-id="2152c-110">Uma matriz contendo os `array[1..Length(array) - 1]` elementos.</span><span class="sxs-lookup"><span data-stu-id="2152c-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2152c-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2152c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2152c-112">'T</span><span class="sxs-lookup"><span data-stu-id="2152c-112">'T</span></span>

<span data-ttu-id="2152c-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="2152c-113">The type of the array elements.</span></span>