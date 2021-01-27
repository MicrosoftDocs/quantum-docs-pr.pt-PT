---
uid: Microsoft.Quantum.Canon.RepeatA
title: Operação RepeatA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852229"
---
# <a name="repeata-operation"></a><span data-ttu-id="9c87c-102">Operação RepeatA</span><span class="sxs-lookup"><span data-stu-id="9c87c-102">RepeatA operation</span></span>

<span data-ttu-id="9c87c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c87c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c87c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c87c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c87c-105">Repete uma operação um dado número de vezes.</span><span class="sxs-lookup"><span data-stu-id="9c87c-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9c87c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9c87c-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="9c87c-107">op : 'TInput = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="9c87c-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9c87c-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="9c87c-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="9c87c-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c87c-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c87c-110">O número de vezes para `op` ligar.</span><span class="sxs-lookup"><span data-stu-id="9c87c-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="9c87c-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="9c87c-111">input : 'TInput</span></span>

<span data-ttu-id="9c87c-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="9c87c-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c87c-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c87c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c87c-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9c87c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="9c87c-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="9c87c-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="9c87c-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9c87c-116">Example</span></span>

<span data-ttu-id="9c87c-117">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="9c87c-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="9c87c-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9c87c-118">See Also</span></span>

- [<span data-ttu-id="9c87c-119">Microsoft.Quantum.Arrays.DrawMany</span><span class="sxs-lookup"><span data-stu-id="9c87c-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="9c87c-120">Microsoft.Quantum.Canon.Repeat</span><span class="sxs-lookup"><span data-stu-id="9c87c-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="9c87c-121">Microsoft.Quantum.Canon.RepeatC</span><span class="sxs-lookup"><span data-stu-id="9c87c-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="9c87c-122">Microsoft.Quantum.Canon.RepeatCA</span><span class="sxs-lookup"><span data-stu-id="9c87c-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)