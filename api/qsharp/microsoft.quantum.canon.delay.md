---
uid: Microsoft.Quantum.Canon.Delay
title: Atrasar operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716320"
---
# <a name="delay-operation"></a><span data-ttu-id="e75fa-102">Atrasar operação</span><span class="sxs-lookup"><span data-stu-id="e75fa-102">Delay operation</span></span>

<span data-ttu-id="e75fa-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e75fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e75fa-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e75fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e75fa-105">Aplica uma determinada operação com um atraso.</span><span class="sxs-lookup"><span data-stu-id="e75fa-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="e75fa-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e75fa-106">Description</span></span>

<span data-ttu-id="e75fa-107">Dada a operação e uma entrada para essa operação, aplica a operação assim que for fornecida uma entrada adicional.</span><span class="sxs-lookup"><span data-stu-id="e75fa-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="e75fa-108">Em particular, a expressão `Delay(op, arg, _)` é uma operação que se aplica `op` quando é `arg` chamada.</span><span class="sxs-lookup"><span data-stu-id="e75fa-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="e75fa-109">A expressão `Delay(op,arg,_)` permite atrasar a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="e75fa-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="e75fa-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="e75fa-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="e75fa-111">op : 'T => 'U</span><span class="sxs-lookup"><span data-stu-id="e75fa-111">op : 'T => 'U</span></span> 

<span data-ttu-id="e75fa-112">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="e75fa-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="e75fa-113">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="e75fa-113">arg : 'T</span></span>

<span data-ttu-id="e75fa-114">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="e75fa-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="e75fa-115">aux : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e75fa-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="e75fa-116">Argumento usado para atrasar a aplicação de operação utilizando aplicação parcial.</span><span class="sxs-lookup"><span data-stu-id="e75fa-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="e75fa-117">Saída : 'U</span><span class="sxs-lookup"><span data-stu-id="e75fa-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e75fa-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e75fa-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e75fa-119">'T</span><span class="sxs-lookup"><span data-stu-id="e75fa-119">'T</span></span>

<span data-ttu-id="e75fa-120">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="e75fa-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="e75fa-121">'U</span><span class="sxs-lookup"><span data-stu-id="e75fa-121">'U</span></span>

<span data-ttu-id="e75fa-122">O tipo de retorno da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="e75fa-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e75fa-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e75fa-123">See Also</span></span>

- [<span data-ttu-id="e75fa-124">Microsoft.Quantum.Canon.DelayC</span><span class="sxs-lookup"><span data-stu-id="e75fa-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="e75fa-125">Microsoft.Quantum.Canon.Delaya</span><span class="sxs-lookup"><span data-stu-id="e75fa-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="e75fa-126">Microsoft.Quantum.Canon.DelayCA</span><span class="sxs-lookup"><span data-stu-id="e75fa-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="e75fa-127">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="e75fa-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)