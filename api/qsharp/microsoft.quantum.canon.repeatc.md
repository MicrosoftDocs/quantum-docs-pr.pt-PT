---
uid: Microsoft.Quantum.Canon.RepeatC
title: Operação RepeatC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 30fd172584b36601c4b81deff494cf55964518f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205444"
---
# <a name="repeatc-operation"></a><span data-ttu-id="f9cd4-102">Operação RepeatC</span><span class="sxs-lookup"><span data-stu-id="f9cd4-102">RepeatC operation</span></span>

<span data-ttu-id="f9cd4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9cd4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9cd4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9cd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9cd4-105">Repete uma operação um dado número de vezes.</span><span class="sxs-lookup"><span data-stu-id="f9cd4-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f9cd4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9cd4-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="f9cd4-107">op : 'TInput = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="f9cd4-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f9cd4-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="f9cd4-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="f9cd4-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9cd4-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9cd4-110">O número de vezes para `op` ligar.</span><span class="sxs-lookup"><span data-stu-id="f9cd4-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="f9cd4-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="f9cd4-111">input : 'TInput</span></span>

<span data-ttu-id="f9cd4-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="f9cd4-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9cd4-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9cd4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9cd4-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f9cd4-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="f9cd4-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="f9cd4-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="f9cd4-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f9cd4-116">See Also</span></span>

- [<span data-ttu-id="f9cd4-117">Microsoft.Quantum.Arrays.DrawMany</span><span class="sxs-lookup"><span data-stu-id="f9cd4-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="f9cd4-118">Microsoft.Quantum.Canon.Repeat</span><span class="sxs-lookup"><span data-stu-id="f9cd4-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="f9cd4-119">Microsoft.Quantum.Canon.Repeata</span><span class="sxs-lookup"><span data-stu-id="f9cd4-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="f9cd4-120">Microsoft.Quantum.Canon.RepeatCA</span><span class="sxs-lookup"><span data-stu-id="f9cd4-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)