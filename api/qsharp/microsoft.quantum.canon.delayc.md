---
uid: Microsoft.Quantum.Canon.DelayC
title: Operação DelayC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: eba4c3bd9f472910e30e5ac8334f09471a685c5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840626"
---
# <a name="delayc-operation"></a><span data-ttu-id="8a1d2-102">Operação DelayC</span><span class="sxs-lookup"><span data-stu-id="8a1d2-102">DelayC operation</span></span>

<span data-ttu-id="8a1d2-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a1d2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a1d2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a1d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a1d2-105">Aplica uma determinada operação com um atraso.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8a1d2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a1d2-106">Description</span></span>

<span data-ttu-id="8a1d2-107">Dada a operação e uma entrada para essa operação, aplica a operação assim que for fornecida uma entrada adicional.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="8a1d2-108">Em particular, a expressão `Delay(op, arg, _)` é uma operação que se aplica `op` quando é `arg` chamada.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="8a1d2-109">A expressão `Delay(op,arg,_)` permite atrasar a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="8a1d2-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="8a1d2-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a1d2-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8a1d2-111">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="8a1d2-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8a1d2-112">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="8a1d2-113">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="8a1d2-113">arg : 'T</span></span>

<span data-ttu-id="8a1d2-114">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="8a1d2-115">aux : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a1d2-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="8a1d2-116">Argumento usado para atrasar a aplicação de operação utilizando aplicação parcial.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a1d2-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a1d2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8a1d2-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8a1d2-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a1d2-119">'T</span><span class="sxs-lookup"><span data-stu-id="8a1d2-119">'T</span></span>

<span data-ttu-id="8a1d2-120">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="8a1d2-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a1d2-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8a1d2-121">See Also</span></span>

- [<span data-ttu-id="8a1d2-122">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="8a1d2-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="8a1d2-123">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="8a1d2-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)