---
uid: Microsoft.Quantum.Arrays.Head
title: Função da cabeça
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848578"
---
# <a name="head-function"></a><span data-ttu-id="796de-102">Função da cabeça</span><span class="sxs-lookup"><span data-stu-id="796de-102">Head function</span></span>

<span data-ttu-id="796de-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="796de-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="796de-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="796de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="796de-105">Devolve o primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="796de-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="796de-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="796de-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="796de-107">matriz : 'A].</span><span class="sxs-lookup"><span data-stu-id="796de-107">array : 'A[]</span></span>

<span data-ttu-id="796de-108">Matriz do qual o primeiro elemento é tomado.</span><span class="sxs-lookup"><span data-stu-id="796de-108">Array of which the first element is taken.</span></span> <span data-ttu-id="796de-109">A matriz deve ter comprimento mínimo de 1.</span><span class="sxs-lookup"><span data-stu-id="796de-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="796de-110">Saída : 'A</span><span class="sxs-lookup"><span data-stu-id="796de-110">Output : 'A</span></span>

<span data-ttu-id="796de-111">O primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="796de-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="796de-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="796de-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="796de-113">'A</span><span class="sxs-lookup"><span data-stu-id="796de-113">'A</span></span>

<span data-ttu-id="796de-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="796de-114">The type of the array elements.</span></span>