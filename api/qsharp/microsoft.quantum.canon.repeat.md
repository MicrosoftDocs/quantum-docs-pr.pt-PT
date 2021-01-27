---
uid: Microsoft.Quantum.Canon.Repeat
title: Operação repetida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 40ee191e8d9044f33aa1621303c70f7e0847e8f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852251"
---
# <a name="repeat-operation"></a><span data-ttu-id="0cb71-102">Operação repetida</span><span class="sxs-lookup"><span data-stu-id="0cb71-102">Repeat operation</span></span>

<span data-ttu-id="0cb71-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0cb71-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0cb71-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0cb71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0cb71-105">Repete uma operação um dado número de vezes.</span><span class="sxs-lookup"><span data-stu-id="0cb71-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="0cb71-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0cb71-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="0cb71-107">op : 'TInput = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0cb71-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0cb71-108">A operação a ser convocada repetidamente.</span><span class="sxs-lookup"><span data-stu-id="0cb71-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="0cb71-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0cb71-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0cb71-110">O número de vezes para `op` ligar.</span><span class="sxs-lookup"><span data-stu-id="0cb71-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="0cb71-111">entrada : 'TInput</span><span class="sxs-lookup"><span data-stu-id="0cb71-111">input : 'TInput</span></span>

<span data-ttu-id="0cb71-112">A entrada a passar para `op` .</span><span class="sxs-lookup"><span data-stu-id="0cb71-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cb71-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cb71-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0cb71-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0cb71-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0cb71-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="0cb71-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="0cb71-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0cb71-116">Example</span></span>

<span data-ttu-id="0cb71-117">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="0cb71-117">The following are equivalent:</span></span>

```qsharp
Repeat(U, 17, target);
(Bound(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="0cb71-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0cb71-118">See Also</span></span>

- [<span data-ttu-id="0cb71-119">Microsoft.Quantum.Arrays.DrawMany</span><span class="sxs-lookup"><span data-stu-id="0cb71-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="0cb71-120">Microsoft.Quantum.Canon.Repeata</span><span class="sxs-lookup"><span data-stu-id="0cb71-120">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="0cb71-121">Microsoft.Quantum.Canon.RepeatC</span><span class="sxs-lookup"><span data-stu-id="0cb71-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="0cb71-122">Microsoft.Quantum.Canon.RepeatCA</span><span class="sxs-lookup"><span data-stu-id="0cb71-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)