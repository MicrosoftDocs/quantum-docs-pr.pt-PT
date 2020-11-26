---
uid: Microsoft.Quantum.Arrays.Chunks
title: Função de pedaços
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221611"
---
# <a name="chunks-function"></a><span data-ttu-id="2febf-102">Função de pedaços</span><span class="sxs-lookup"><span data-stu-id="2febf-102">Chunks function</span></span>

<span data-ttu-id="2febf-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2febf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2febf-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2febf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2febf-105">Divide uma matriz em várias partes de comprimento igual.</span><span class="sxs-lookup"><span data-stu-id="2febf-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="2febf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2febf-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="2febf-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2febf-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2febf-108">O comprimento de cada pedaço.</span><span class="sxs-lookup"><span data-stu-id="2febf-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="2febf-109">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="2febf-109">arr : 'T[]</span></span>

<span data-ttu-id="2febf-110">A matriz a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="2febf-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="2febf-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="2febf-111">Output : 'T[][]</span></span>

<span data-ttu-id="2febf-112">Uma matriz contendo cada pedaço da matriz original.</span><span class="sxs-lookup"><span data-stu-id="2febf-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2febf-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2febf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2febf-114">'T</span><span class="sxs-lookup"><span data-stu-id="2febf-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2febf-115">Observações</span><span class="sxs-lookup"><span data-stu-id="2febf-115">Remarks</span></span>

<span data-ttu-id="2febf-116">Note que o último elemento da saída pode ser mais curto do que `nElements` se `Length(arr)` não for divisível por `nElements` .</span><span class="sxs-lookup"><span data-stu-id="2febf-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>