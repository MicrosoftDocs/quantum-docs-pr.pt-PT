---
uid: Microsoft.Quantum.Arrays.Tail
title: Função da cauda
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220098"
---
# <a name="tail-function"></a><span data-ttu-id="c869f-102">Função da cauda</span><span class="sxs-lookup"><span data-stu-id="c869f-102">Tail function</span></span>

<span data-ttu-id="c869f-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c869f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c869f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c869f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c869f-105">Devolve o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="c869f-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="c869f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c869f-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="c869f-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="c869f-107">array : 'A[]</span></span>

<span data-ttu-id="c869f-108">Matriz do qual o último elemento é tomado.</span><span class="sxs-lookup"><span data-stu-id="c869f-108">Array of which the last element is taken.</span></span> <span data-ttu-id="c869f-109">A matriz deve ter comprimento mínimo de 1.</span><span class="sxs-lookup"><span data-stu-id="c869f-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="c869f-110">Saída : 'A</span><span class="sxs-lookup"><span data-stu-id="c869f-110">Output : 'A</span></span>

<span data-ttu-id="c869f-111">O último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="c869f-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c869f-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c869f-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="c869f-113">'A</span><span class="sxs-lookup"><span data-stu-id="c869f-113">'A</span></span>

<span data-ttu-id="c869f-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="c869f-114">The type of the array elements.</span></span>