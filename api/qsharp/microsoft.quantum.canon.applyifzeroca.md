---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Aplicação OperaçãoIfZeroCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4baae1fe7d615cbbf01935b4eca05fe947ff296e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218466"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="031e5-102">Aplicação OperaçãoIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="031e5-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="031e5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="031e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="031e5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="031e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="031e5-105">Aplica uma operação unitária condicionada a um valor de resultado clássico ser zero.</span><span class="sxs-lookup"><span data-stu-id="031e5-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="031e5-106">Description</span><span class="sxs-lookup"><span data-stu-id="031e5-106">Description</span></span>

<span data-ttu-id="031e5-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="031e5-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="031e5-108">Se, `One` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="031e5-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="031e5-109">O `CA` sufixo indica que a operação a aplicar é unitária (controlável e adjacente).</span><span class="sxs-lookup"><span data-stu-id="031e5-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="031e5-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="031e5-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="031e5-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="031e5-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="031e5-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="031e5-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="031e5-113">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="031e5-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="031e5-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="031e5-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="031e5-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="031e5-115">target : 'T</span></span>

<span data-ttu-id="031e5-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="031e5-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="031e5-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="031e5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="031e5-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="031e5-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="031e5-119">'T</span><span class="sxs-lookup"><span data-stu-id="031e5-119">'T</span></span>

<span data-ttu-id="031e5-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="031e5-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="031e5-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="031e5-121">See Also</span></span>

- [<span data-ttu-id="031e5-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="031e5-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="031e5-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="031e5-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="031e5-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="031e5-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)