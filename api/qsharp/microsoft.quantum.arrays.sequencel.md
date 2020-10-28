---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Função SequenceL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718882"
---
# <a name="sequencel-function"></a><span data-ttu-id="9151f-102">Função SequenceL</span><span class="sxs-lookup"><span data-stu-id="9151f-102">SequenceL function</span></span>

<span data-ttu-id="9151f-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9151f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9151f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9151f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9151f-105">Obtenha uma série de inteiros num dado intervalo.</span><span class="sxs-lookup"><span data-stu-id="9151f-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="9151f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9151f-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="9151f-107">de : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9151f-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9151f-108">Um índice de início inclusivo do intervalo.</span><span class="sxs-lookup"><span data-stu-id="9151f-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="9151f-109">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9151f-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9151f-110">Um índice final inclusivo do intervalo que não é menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="9151f-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="9151f-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="9151f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="9151f-112">Uma matriz contendo a sequência de `from` `from + 1` números, ... ..., `to` .</span><span class="sxs-lookup"><span data-stu-id="9151f-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9151f-113">Observações</span><span class="sxs-lookup"><span data-stu-id="9151f-113">Remarks</span></span>

<span data-ttu-id="9151f-114">A diferença entre `from` e deve caber num `to` `Int` valor.</span><span class="sxs-lookup"><span data-stu-id="9151f-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>