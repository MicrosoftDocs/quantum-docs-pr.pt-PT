---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846212"
---
# <a name="drawmany-operation"></a><span data-ttu-id="0829a-102">DrawMany operação</span><span class="sxs-lookup"><span data-stu-id="0829a-102">DrawMany operation</span></span>

<span data-ttu-id="0829a-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0829a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0829a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0829a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0829a-105">Repete uma operação para um determinado número de amostras, recolhendo as suas saídas numa matriz.</span><span class="sxs-lookup"><span data-stu-id="0829a-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="0829a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0829a-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="0829a-107">op : 'TInput => 'TOutput</span><span class="sxs-lookup"><span data-stu-id="0829a-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="0829a-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="0829a-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="0829a-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0829a-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0829a-110">O número de amostras de chamadas `op` para recolher.</span><span class="sxs-lookup"><span data-stu-id="0829a-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="0829a-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="0829a-111">input : 'TInput</span></span>

<span data-ttu-id="0829a-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="0829a-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="0829a-113">Saída : 'TOutput[]</span><span class="sxs-lookup"><span data-stu-id="0829a-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0829a-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0829a-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0829a-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="0829a-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="0829a-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="0829a-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="0829a-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0829a-117">Example</span></span>

<span data-ttu-id="0829a-118">As seguintes amostras de um inteiro, dada uma operação que amostra um pedaço de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0829a-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="0829a-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0829a-119">See Also</span></span>

- [<span data-ttu-id="0829a-120">Microsoft.Quantum.Canon.Repeat</span><span class="sxs-lookup"><span data-stu-id="0829a-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)