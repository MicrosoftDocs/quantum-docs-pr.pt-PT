---
uid: Microsoft.Quantum.Canon.RepeatC
title: Operação RepeatC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 8dc178374bdc9f8bf9f8aed57b9ae9a56995dec6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715553"
---
# <a name="repeatc-operation"></a><span data-ttu-id="1f8f3-102">Operação RepeatC</span><span class="sxs-lookup"><span data-stu-id="1f8f3-102">RepeatC operation</span></span>

<span data-ttu-id="1f8f3-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f8f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f8f3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f8f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f8f3-105">Repete uma operação um dado número de vezes.</span><span class="sxs-lookup"><span data-stu-id="1f8f3-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="1f8f3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f8f3-106">Input</span></span>

### <a name="op--tinput--unit-ctl"></a><span data-ttu-id="1f8f3-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="1f8f3-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="1f8f3-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="1f8f3-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="1f8f3-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f8f3-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f8f3-110">O número de vezes para `op` ligar.</span><span class="sxs-lookup"><span data-stu-id="1f8f3-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="1f8f3-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="1f8f3-111">input : 'TInput</span></span>

<span data-ttu-id="1f8f3-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="1f8f3-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f8f3-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f8f3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f8f3-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1f8f3-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="1f8f3-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="1f8f3-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="1f8f3-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f8f3-116">See Also</span></span>

- [<span data-ttu-id="1f8f3-117">Microsoft.Quantum.Arrays.DrawMany</span><span class="sxs-lookup"><span data-stu-id="1f8f3-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="1f8f3-118">Microsoft.Quantum.Canon.Repeat</span><span class="sxs-lookup"><span data-stu-id="1f8f3-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="1f8f3-119">Microsoft.Quantum.Canon.Repeata</span><span class="sxs-lookup"><span data-stu-id="1f8f3-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="1f8f3-120">Microsoft.Quantum.Canon.RepeatCA</span><span class="sxs-lookup"><span data-stu-id="1f8f3-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)