---
uid: Microsoft.Quantum.Arrays.Head
title: Função da cabeça
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719183"
---
# <a name="head-function"></a><span data-ttu-id="a761a-102">Função da cabeça</span><span class="sxs-lookup"><span data-stu-id="a761a-102">Head function</span></span>

<span data-ttu-id="a761a-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a761a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a761a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a761a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a761a-105">Devolve o primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="a761a-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="a761a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a761a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a761a-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="a761a-107">array : 'A[]</span></span>

<span data-ttu-id="a761a-108">Matriz do qual o primeiro elemento é tomado.</span><span class="sxs-lookup"><span data-stu-id="a761a-108">Array of which the first element is taken.</span></span> <span data-ttu-id="a761a-109">A matriz deve ter comprimento mínimo de 1.</span><span class="sxs-lookup"><span data-stu-id="a761a-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="a761a-110">Saída : 'A</span><span class="sxs-lookup"><span data-stu-id="a761a-110">Output : 'A</span></span>

<span data-ttu-id="a761a-111">O primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="a761a-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a761a-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a761a-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a761a-113">'A</span><span class="sxs-lookup"><span data-stu-id="a761a-113">'A</span></span>

<span data-ttu-id="a761a-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="a761a-114">The type of the array elements.</span></span>