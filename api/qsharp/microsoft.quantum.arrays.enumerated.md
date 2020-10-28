---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Função enumerada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719303"
---
# <a name="enumerated-function"></a><span data-ttu-id="f4566-102">Função enumerada</span><span class="sxs-lookup"><span data-stu-id="f4566-102">Enumerated function</span></span>

<span data-ttu-id="f4566-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f4566-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f4566-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4566-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4566-105">Dada uma matriz, devolve uma nova matriz contendo elementos da matriz original juntamente com os índices de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f4566-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="f4566-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f4566-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="f4566-107">matriz : 'TElement[]</span><span class="sxs-lookup"><span data-stu-id="f4566-107">array : 'TElement[]</span></span>

<span data-ttu-id="f4566-108">Uma matriz cujos elementos devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="f4566-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="f4566-109">Saída :[(Int](xref:microsoft.quantum.lang-ref.int)'TElement)[]</span><span class="sxs-lookup"><span data-stu-id="f4566-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="f4566-110">Uma nova matriz contendo elementos da matriz original juntamente com os seus índices.</span><span class="sxs-lookup"><span data-stu-id="f4566-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4566-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f4566-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="f4566-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="f4566-112">'TElement</span></span>

<span data-ttu-id="f4566-113">O tipo de elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="f4566-113">The type of elements of the array.</span></span>