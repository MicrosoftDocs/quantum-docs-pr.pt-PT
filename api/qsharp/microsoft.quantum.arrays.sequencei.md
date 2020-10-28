---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Função Sequênciai
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718895"
---
# <a name="sequencei-function"></a><span data-ttu-id="d5a0d-102">Função Sequênciai</span><span class="sxs-lookup"><span data-stu-id="d5a0d-102">SequenceI function</span></span>

<span data-ttu-id="d5a0d-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d5a0d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d5a0d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5a0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5a0d-105">Obtenha uma série de inteiros num dado intervalo.</span><span class="sxs-lookup"><span data-stu-id="d5a0d-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="d5a0d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d5a0d-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="d5a0d-107">de : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5a0d-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5a0d-108">Um índice de início inclusivo do intervalo.</span><span class="sxs-lookup"><span data-stu-id="d5a0d-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="d5a0d-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5a0d-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5a0d-110">Um índice final inclusivo do intervalo que não é menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="d5a0d-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="d5a0d-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d5a0d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d5a0d-112">Uma matriz contendo a sequência de `from` `from + 1` números, ... ..., `to` .</span><span class="sxs-lookup"><span data-stu-id="d5a0d-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>