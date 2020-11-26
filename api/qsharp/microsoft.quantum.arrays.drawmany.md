---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210000"
---
# <a name="drawmany-operation"></a><span data-ttu-id="1f79c-102">DrawMany operação</span><span class="sxs-lookup"><span data-stu-id="1f79c-102">DrawMany operation</span></span>

<span data-ttu-id="1f79c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1f79c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1f79c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f79c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f79c-105">Repete uma operação para um determinado número de amostras, recolhendo as suas saídas numa matriz.</span><span class="sxs-lookup"><span data-stu-id="1f79c-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="1f79c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f79c-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="1f79c-107">op : 'TInput => 'TOutput</span><span class="sxs-lookup"><span data-stu-id="1f79c-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="1f79c-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="1f79c-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="1f79c-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f79c-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f79c-110">O número de amostras de chamadas `op` para recolher.</span><span class="sxs-lookup"><span data-stu-id="1f79c-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="1f79c-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="1f79c-111">input : 'TInput</span></span>

<span data-ttu-id="1f79c-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="1f79c-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="1f79c-113">Saída : 'TOutput[]</span><span class="sxs-lookup"><span data-stu-id="1f79c-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f79c-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1f79c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="1f79c-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="1f79c-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="1f79c-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="1f79c-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="1f79c-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f79c-117">See Also</span></span>

- [<span data-ttu-id="1f79c-118">Microsoft.Quantum.Canon.Repeat</span><span class="sxs-lookup"><span data-stu-id="1f79c-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)