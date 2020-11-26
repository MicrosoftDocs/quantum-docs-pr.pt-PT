---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Função SequenceL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220268"
---
# <a name="sequencel-function"></a><span data-ttu-id="d6827-102">Função SequenceL</span><span class="sxs-lookup"><span data-stu-id="d6827-102">SequenceL function</span></span>

<span data-ttu-id="d6827-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d6827-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d6827-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6827-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6827-105">Obtenha uma série de inteiros num dado intervalo.</span><span class="sxs-lookup"><span data-stu-id="d6827-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="d6827-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d6827-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="d6827-107">de : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d6827-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d6827-108">Um índice de início inclusivo do intervalo.</span><span class="sxs-lookup"><span data-stu-id="d6827-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="d6827-109">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d6827-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d6827-110">Um índice final inclusivo do intervalo que não é menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="d6827-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="d6827-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="d6827-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="d6827-112">Uma matriz contendo a sequência de `from` `from + 1` números, ... ..., `to` .</span><span class="sxs-lookup"><span data-stu-id="d6827-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6827-113">Observações</span><span class="sxs-lookup"><span data-stu-id="d6827-113">Remarks</span></span>

<span data-ttu-id="d6827-114">A diferença entre `from` e deve caber num `to` `Int` valor.</span><span class="sxs-lookup"><span data-stu-id="d6827-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>