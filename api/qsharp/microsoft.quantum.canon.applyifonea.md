---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: AplicarIfOneA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844935"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="70211-102">AplicarIfOneA operação</span><span class="sxs-lookup"><span data-stu-id="70211-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="70211-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70211-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70211-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70211-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70211-105">Aplica uma operação contígua condicionada a um valor de resultado clássico sendo um.</span><span class="sxs-lookup"><span data-stu-id="70211-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="70211-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="70211-106">Description</span></span>

<span data-ttu-id="70211-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="70211-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="70211-108">Se, `Zero` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="70211-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="70211-109">O `A` sufixo indica que a operação a aplicar é adjacente.</span><span class="sxs-lookup"><span data-stu-id="70211-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="70211-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="70211-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="70211-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="70211-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="70211-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="70211-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="70211-113">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="70211-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="70211-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="70211-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="70211-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="70211-115">target : 'T</span></span>

<span data-ttu-id="70211-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="70211-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70211-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70211-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="70211-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="70211-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70211-119">'T</span><span class="sxs-lookup"><span data-stu-id="70211-119">'T</span></span>

<span data-ttu-id="70211-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="70211-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="70211-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="70211-121">See Also</span></span>

- [<span data-ttu-id="70211-122">Microsoft.Quantum.Canon.ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="70211-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="70211-123">Microsoft.Quantum.Canon.ApplyIfOnea</span><span class="sxs-lookup"><span data-stu-id="70211-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="70211-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="70211-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)