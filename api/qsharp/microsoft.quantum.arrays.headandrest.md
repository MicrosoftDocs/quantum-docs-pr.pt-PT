---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Função HeadAndRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848553"
---
# <a name="headandrest-function"></a><span data-ttu-id="9afd4-102">Função HeadAndRest</span><span class="sxs-lookup"><span data-stu-id="9afd4-102">HeadAndRest function</span></span>

<span data-ttu-id="9afd4-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9afd4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9afd4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9afd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9afd4-105">Devolve uma tuple de primeiro e todos os elementos restantes da matriz.</span><span class="sxs-lookup"><span data-stu-id="9afd4-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="9afd4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9afd4-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9afd4-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="9afd4-107">array : 'A[]</span></span>

<span data-ttu-id="9afd4-108">Uma matriz com pelo menos um elemento.</span><span class="sxs-lookup"><span data-stu-id="9afd4-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="9afd4-109">Saída : ('A,'A])</span><span class="sxs-lookup"><span data-stu-id="9afd4-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="9afd4-110">Um tuple de primeiro e todos os elementos restantes da matriz.</span><span class="sxs-lookup"><span data-stu-id="9afd4-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9afd4-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9afd4-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9afd4-112">'A</span><span class="sxs-lookup"><span data-stu-id="9afd4-112">'A</span></span>

<span data-ttu-id="9afd4-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="9afd4-113">The type of the array elements.</span></span>