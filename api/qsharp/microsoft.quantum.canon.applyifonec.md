---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Aplicar operaçãoIfOneC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841758"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="f717c-102">Aplicar operaçãoIfOneC</span><span class="sxs-lookup"><span data-stu-id="f717c-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="f717c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f717c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f717c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f717c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f717c-105">Aplica uma operação controlável condicionada a um valor de resultado clássico sendo um.</span><span class="sxs-lookup"><span data-stu-id="f717c-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="f717c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="f717c-106">Description</span></span>

<span data-ttu-id="f717c-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="f717c-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f717c-108">Se, `Zero` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="f717c-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f717c-109">O `C` sufixo indica que a operação a aplicar é controlável.</span><span class="sxs-lookup"><span data-stu-id="f717c-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="f717c-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="f717c-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f717c-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="f717c-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f717c-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="f717c-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f717c-113">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="f717c-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f717c-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f717c-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f717c-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="f717c-115">target : 'T</span></span>

<span data-ttu-id="f717c-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="f717c-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f717c-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f717c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f717c-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f717c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f717c-119">'T</span><span class="sxs-lookup"><span data-stu-id="f717c-119">'T</span></span>

<span data-ttu-id="f717c-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f717c-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f717c-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f717c-121">See Also</span></span>

- [<span data-ttu-id="f717c-122">Microsoft.Quantum.Canon.ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f717c-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f717c-123">Microsoft.Quantum.Canon.ApplyIfOnea</span><span class="sxs-lookup"><span data-stu-id="f717c-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f717c-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f717c-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)