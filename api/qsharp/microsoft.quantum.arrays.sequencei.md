---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Função Sequênciai
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220302"
---
# <a name="sequencei-function"></a><span data-ttu-id="ecf15-102">Função Sequênciai</span><span class="sxs-lookup"><span data-stu-id="ecf15-102">SequenceI function</span></span>

<span data-ttu-id="ecf15-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ecf15-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ecf15-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecf15-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecf15-105">Obtenha uma série de inteiros num dado intervalo.</span><span class="sxs-lookup"><span data-stu-id="ecf15-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="ecf15-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ecf15-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="ecf15-107">de : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecf15-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecf15-108">Um índice de início inclusivo do intervalo.</span><span class="sxs-lookup"><span data-stu-id="ecf15-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="ecf15-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecf15-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecf15-110">Um índice final inclusivo do intervalo que não é menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="ecf15-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ecf15-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ecf15-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ecf15-112">Uma matriz contendo a sequência de `from` `from + 1` números, ... ..., `to` .</span><span class="sxs-lookup"><span data-stu-id="ecf15-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>