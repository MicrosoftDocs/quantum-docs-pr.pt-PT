---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: Aplicação OperaçãoIfElseRCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: 6dfa2a5cf88029ac772b09bc2d36a5f19ef37a14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844943"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="6d7e2-102">Aplicação OperaçãoIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="6d7e2-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="6d7e2-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6d7e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6d7e2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d7e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d7e2-105">Aplica uma de duas operações unitárias, dependendo do valor de um resultado clássico.</span><span class="sxs-lookup"><span data-stu-id="6d7e2-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6d7e2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="6d7e2-106">Description</span></span>

<span data-ttu-id="6d7e2-107">Dado o `result` resultado, aplica a operação `zeroOp` com a sua entrada quando é igual a , e `zeroInput` `result` `Zero` aplica-se `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="6d7e2-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="6d7e2-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="6d7e2-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="6d7e2-109">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="6d7e2-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="6d7e2-110">O resultado da medição utilizado para determinar se `zeroOp` ou `oneOp` é aplicado.</span><span class="sxs-lookup"><span data-stu-id="6d7e2-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="6d7e2-111">zeroOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6d7e2-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6d7e2-112">A operação unitária a aplicar quando `result == Zero` . .</span><span class="sxs-lookup"><span data-stu-id="6d7e2-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="6d7e2-113">zeroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="6d7e2-113">zeroInput : 'T</span></span>

<span data-ttu-id="6d7e2-114">A entrada a fornecer `zeroOp` quando `result == Zero` . .</span><span class="sxs-lookup"><span data-stu-id="6d7e2-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj--ctl"></a><span data-ttu-id="6d7e2-115">oneOp : 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6d7e2-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6d7e2-116">A operação unitária a aplicar quando `result == One` . .</span><span class="sxs-lookup"><span data-stu-id="6d7e2-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="6d7e2-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="6d7e2-117">oneInput : 'U</span></span>

<span data-ttu-id="6d7e2-118">A entrada a fornecer `oneOp` quando `result == One` . .</span><span class="sxs-lookup"><span data-stu-id="6d7e2-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d7e2-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d7e2-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6d7e2-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6d7e2-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6d7e2-121">'T</span><span class="sxs-lookup"><span data-stu-id="6d7e2-121">'T</span></span>

<span data-ttu-id="6d7e2-122">O tipo de entrada da operação `zeroOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="6d7e2-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="6d7e2-123">'U</span><span class="sxs-lookup"><span data-stu-id="6d7e2-123">'U</span></span>

<span data-ttu-id="6d7e2-124">O tipo de entrada da operação `oneOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="6d7e2-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d7e2-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6d7e2-125">See Also</span></span>

- [<span data-ttu-id="6d7e2-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="6d7e2-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="6d7e2-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="6d7e2-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="6d7e2-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="6d7e2-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="6d7e2-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="6d7e2-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="6d7e2-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="6d7e2-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)