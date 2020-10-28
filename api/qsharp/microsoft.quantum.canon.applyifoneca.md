---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: AplicarIfOneCA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 973dd3c5f9f3e9ad03c0626a38779f499b7ce657
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718070"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="d3331-102">AplicarIfOneCA operação</span><span class="sxs-lookup"><span data-stu-id="d3331-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="d3331-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d3331-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d3331-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3331-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3331-105">Aplica uma operação unitária condicionada a um valor de resultado clássico sendo um.</span><span class="sxs-lookup"><span data-stu-id="d3331-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="d3331-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d3331-106">Description</span></span>

<span data-ttu-id="d3331-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="d3331-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="d3331-108">Se, `Zero` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="d3331-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="d3331-109">O `CA` sufixo indica que a operação a aplicar é unitária (controlável e adjacente).</span><span class="sxs-lookup"><span data-stu-id="d3331-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="d3331-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3331-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="d3331-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="d3331-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="d3331-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="d3331-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="d3331-113">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="d3331-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d3331-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="d3331-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="d3331-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="d3331-115">target : 'T</span></span>

<span data-ttu-id="d3331-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="d3331-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3331-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3331-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d3331-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d3331-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d3331-119">'T</span><span class="sxs-lookup"><span data-stu-id="d3331-119">'T</span></span>

<span data-ttu-id="d3331-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="d3331-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3331-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d3331-121">See Also</span></span>

- [<span data-ttu-id="d3331-122">Microsoft.Quantum.Canon.ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="d3331-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="d3331-123">Microsoft.Quantum.Canon.ApplyIfOnea</span><span class="sxs-lookup"><span data-stu-id="d3331-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="d3331-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="d3331-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)