---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Aplicação OperaçãoIfZeroC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718014"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="298db-102">Aplicação OperaçãoIfZeroC</span><span class="sxs-lookup"><span data-stu-id="298db-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="298db-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="298db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="298db-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="298db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="298db-105">Aplica uma operação controlável condicionada a um valor de resultado clássico sendo zero.</span><span class="sxs-lookup"><span data-stu-id="298db-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="298db-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="298db-106">Description</span></span>

<span data-ttu-id="298db-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="298db-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="298db-108">Se, `One` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="298db-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="298db-109">O `C` sufixo indica que a operação a aplicar é controlável.</span><span class="sxs-lookup"><span data-stu-id="298db-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="298db-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="298db-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="298db-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="298db-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="298db-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="298db-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="298db-113">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="298db-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="298db-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="298db-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="298db-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="298db-115">target : 'T</span></span>

<span data-ttu-id="298db-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="298db-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="298db-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="298db-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="298db-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="298db-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="298db-119">'T</span><span class="sxs-lookup"><span data-stu-id="298db-119">'T</span></span>

<span data-ttu-id="298db-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="298db-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="298db-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="298db-121">See Also</span></span>

- [<span data-ttu-id="298db-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="298db-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="298db-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="298db-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="298db-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="298db-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)