---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Função HeadAndRest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221084"
---
# <a name="headandrest-function"></a><span data-ttu-id="e7fd8-102">Função HeadAndRest</span><span class="sxs-lookup"><span data-stu-id="e7fd8-102">HeadAndRest function</span></span>

<span data-ttu-id="e7fd8-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e7fd8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e7fd8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7fd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7fd8-105">Devolve uma tuple de primeiro e todos os elementos restantes da matriz.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="e7fd8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7fd8-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="e7fd8-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="e7fd8-107">array : 'A[]</span></span>

<span data-ttu-id="e7fd8-108">Uma matriz com pelo menos um elemento.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="e7fd8-109">Saída : ('A,'A])</span><span class="sxs-lookup"><span data-stu-id="e7fd8-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="e7fd8-110">Um tuple de primeiro e todos os elementos restantes da matriz.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e7fd8-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e7fd8-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="e7fd8-112">'A</span><span class="sxs-lookup"><span data-stu-id="e7fd8-112">'A</span></span>

<span data-ttu-id="e7fd8-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-113">The type of the array elements.</span></span>