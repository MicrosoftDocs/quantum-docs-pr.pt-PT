---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Função MostAndTail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718991"
---
# <a name="mostandtail-function"></a><span data-ttu-id="cf907-102">Função MostAndTail</span><span class="sxs-lookup"><span data-stu-id="cf907-102">MostAndTail function</span></span>

<span data-ttu-id="cf907-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cf907-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cf907-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf907-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf907-105">Devolve uma tuple de todos, menos um e o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="cf907-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="cf907-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf907-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="cf907-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="cf907-107">array : 'A[]</span></span>

<span data-ttu-id="cf907-108">Uma matriz com pelo menos um elemento.</span><span class="sxs-lookup"><span data-stu-id="cf907-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="cf907-109">Saída : ('A],'A)</span><span class="sxs-lookup"><span data-stu-id="cf907-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="cf907-110">Uma tuple de todos, menos um e o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="cf907-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cf907-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="cf907-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="cf907-112">'A</span><span class="sxs-lookup"><span data-stu-id="cf907-112">'A</span></span>

<span data-ttu-id="cf907-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="cf907-113">The type of the array elements.</span></span>