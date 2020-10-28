---
uid: Microsoft.Quantum.Arrays.Tail
title: Função da cauda
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718822"
---
# <a name="tail-function"></a><span data-ttu-id="ad267-102">Função da cauda</span><span class="sxs-lookup"><span data-stu-id="ad267-102">Tail function</span></span>

<span data-ttu-id="ad267-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ad267-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ad267-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad267-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad267-105">Devolve o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="ad267-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="ad267-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ad267-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="ad267-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="ad267-107">array : 'A[]</span></span>

<span data-ttu-id="ad267-108">Matriz do qual o último elemento é tomado.</span><span class="sxs-lookup"><span data-stu-id="ad267-108">Array of which the last element is taken.</span></span> <span data-ttu-id="ad267-109">A matriz deve ter comprimento mínimo de 1.</span><span class="sxs-lookup"><span data-stu-id="ad267-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="ad267-110">Saída : 'A</span><span class="sxs-lookup"><span data-stu-id="ad267-110">Output : 'A</span></span>

<span data-ttu-id="ad267-111">O último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="ad267-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ad267-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ad267-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="ad267-113">'A</span><span class="sxs-lookup"><span data-stu-id="ad267-113">'A</span></span>

<span data-ttu-id="ad267-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="ad267-114">The type of the array elements.</span></span>