---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Função MostAndTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845595"
---
# <a name="mostandtail-function"></a><span data-ttu-id="4941f-102">Função MostAndTail</span><span class="sxs-lookup"><span data-stu-id="4941f-102">MostAndTail function</span></span>

<span data-ttu-id="4941f-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4941f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4941f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4941f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4941f-105">Devolve uma tuple de todos, menos um e o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="4941f-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="4941f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4941f-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="4941f-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="4941f-107">array : 'A[]</span></span>

<span data-ttu-id="4941f-108">Uma matriz com pelo menos um elemento.</span><span class="sxs-lookup"><span data-stu-id="4941f-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="4941f-109">Saída : ('A],'A)</span><span class="sxs-lookup"><span data-stu-id="4941f-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="4941f-110">Uma tuple de todos, menos um e o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="4941f-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4941f-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4941f-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="4941f-112">'A</span><span class="sxs-lookup"><span data-stu-id="4941f-112">'A</span></span>

<span data-ttu-id="4941f-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="4941f-113">The type of the array elements.</span></span>