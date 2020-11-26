---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: AplicarIfOneCA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218585"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="2650e-102">AplicarIfOneCA operação</span><span class="sxs-lookup"><span data-stu-id="2650e-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="2650e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2650e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2650e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2650e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2650e-105">Aplica uma operação unitária condicionada a um valor de resultado clássico sendo um.</span><span class="sxs-lookup"><span data-stu-id="2650e-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2650e-106">Description</span><span class="sxs-lookup"><span data-stu-id="2650e-106">Description</span></span>

<span data-ttu-id="2650e-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="2650e-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="2650e-108">Se, `Zero` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="2650e-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="2650e-109">O `CA` sufixo indica que a operação a aplicar é unitária (controlável e adjacente).</span><span class="sxs-lookup"><span data-stu-id="2650e-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="2650e-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="2650e-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="2650e-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2650e-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="2650e-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="2650e-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="2650e-113">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="2650e-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2650e-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2650e-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="2650e-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="2650e-115">target : 'T</span></span>

<span data-ttu-id="2650e-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="2650e-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2650e-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2650e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2650e-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2650e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2650e-119">'T</span><span class="sxs-lookup"><span data-stu-id="2650e-119">'T</span></span>

<span data-ttu-id="2650e-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2650e-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2650e-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2650e-121">See Also</span></span>

- [<span data-ttu-id="2650e-122">Microsoft.Quantum.Canon.ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="2650e-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="2650e-123">Microsoft.Quantum.Canon.ApplyIfOnea</span><span class="sxs-lookup"><span data-stu-id="2650e-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="2650e-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="2650e-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)