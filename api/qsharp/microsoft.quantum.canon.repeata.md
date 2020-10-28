---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operação RepeatA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 89d34e5a30a61dee392904ce1076605432e21395
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715564"
---
# <a name="repeata-operation"></a><span data-ttu-id="bf324-102">Operação RepeatA</span><span class="sxs-lookup"><span data-stu-id="bf324-102">RepeatA operation</span></span>

<span data-ttu-id="bf324-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf324-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf324-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf324-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf324-105">Repete uma operação um dado número de vezes.</span><span class="sxs-lookup"><span data-stu-id="bf324-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="bf324-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bf324-106">Input</span></span>

### <a name="op--tinput--unit-adj"></a><span data-ttu-id="bf324-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="bf324-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="bf324-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="bf324-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="bf324-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf324-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf324-110">O número de vezes para `op` ligar.</span><span class="sxs-lookup"><span data-stu-id="bf324-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="bf324-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="bf324-111">input : 'TInput</span></span>

<span data-ttu-id="bf324-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="bf324-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf324-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf324-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf324-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bf324-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="bf324-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="bf324-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="bf324-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bf324-116">See Also</span></span>

- [<span data-ttu-id="bf324-117">Microsoft.Quantum.Arrays.DrawMany</span><span class="sxs-lookup"><span data-stu-id="bf324-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="bf324-118">Microsoft.Quantum.Canon.Repeat</span><span class="sxs-lookup"><span data-stu-id="bf324-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="bf324-119">Microsoft.Quantum.Canon.RepeatC</span><span class="sxs-lookup"><span data-stu-id="bf324-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="bf324-120">Microsoft.Quantum.Canon.RepeatCA</span><span class="sxs-lookup"><span data-stu-id="bf324-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)