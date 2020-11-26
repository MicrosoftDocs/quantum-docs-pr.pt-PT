---
uid: Microsoft.Quantum.Canon.DelayC
title: Operação DelayC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216494"
---
# <a name="delayc-operation"></a><span data-ttu-id="1290b-102">Operação DelayC</span><span class="sxs-lookup"><span data-stu-id="1290b-102">DelayC operation</span></span>

<span data-ttu-id="1290b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1290b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1290b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1290b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1290b-105">Aplica uma determinada operação com um atraso.</span><span class="sxs-lookup"><span data-stu-id="1290b-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="1290b-106">Description</span><span class="sxs-lookup"><span data-stu-id="1290b-106">Description</span></span>

<span data-ttu-id="1290b-107">Dada a operação e uma entrada para essa operação, aplica a operação assim que for fornecida uma entrada adicional.</span><span class="sxs-lookup"><span data-stu-id="1290b-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="1290b-108">Em particular, a expressão `Delay(op, arg, _)` é uma operação que se aplica `op` quando é `arg` chamada.</span><span class="sxs-lookup"><span data-stu-id="1290b-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="1290b-109">A expressão `Delay(op,arg,_)` permite atrasar a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="1290b-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="1290b-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="1290b-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1290b-111">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="1290b-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1290b-112">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="1290b-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="1290b-113">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="1290b-113">arg : 'T</span></span>

<span data-ttu-id="1290b-114">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="1290b-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="1290b-115">aux : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1290b-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="1290b-116">Argumento usado para atrasar a aplicação de operação utilizando aplicação parcial.</span><span class="sxs-lookup"><span data-stu-id="1290b-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1290b-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1290b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1290b-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1290b-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1290b-119">'T</span><span class="sxs-lookup"><span data-stu-id="1290b-119">'T</span></span>

<span data-ttu-id="1290b-120">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="1290b-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="1290b-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1290b-121">See Also</span></span>

- [<span data-ttu-id="1290b-122">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="1290b-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="1290b-123">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="1290b-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)