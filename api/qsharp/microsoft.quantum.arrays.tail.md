---
uid: Microsoft.Quantum.Arrays.Tail
title: Função da cauda
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845414"
---
# <a name="tail-function"></a><span data-ttu-id="9165e-102">Função da cauda</span><span class="sxs-lookup"><span data-stu-id="9165e-102">Tail function</span></span>

<span data-ttu-id="9165e-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9165e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9165e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9165e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9165e-105">Devolve o último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="9165e-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="9165e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9165e-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9165e-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="9165e-107">array : 'A[]</span></span>

<span data-ttu-id="9165e-108">Matriz do qual o último elemento é tomado.</span><span class="sxs-lookup"><span data-stu-id="9165e-108">Array of which the last element is taken.</span></span> <span data-ttu-id="9165e-109">A matriz deve ter comprimento mínimo de 1.</span><span class="sxs-lookup"><span data-stu-id="9165e-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="9165e-110">Saída : 'A</span><span class="sxs-lookup"><span data-stu-id="9165e-110">Output : 'A</span></span>

<span data-ttu-id="9165e-111">O último elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="9165e-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9165e-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9165e-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9165e-113">'A</span><span class="sxs-lookup"><span data-stu-id="9165e-113">'A</span></span>

<span data-ttu-id="9165e-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="9165e-114">The type of the array elements.</span></span>