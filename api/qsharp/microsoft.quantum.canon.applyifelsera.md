---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: Aplicação OperaçãoIfElseRA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 0a7683adfa15f787f96c7ae55f94e2c52426df75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845021"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="26eb0-102">Aplicação OperaçãoIfElseRA</span><span class="sxs-lookup"><span data-stu-id="26eb0-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="26eb0-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="26eb0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="26eb0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26eb0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26eb0-105">Aplica uma de duas operações contíguas, dependendo do valor de um resultado clássico.</span><span class="sxs-lookup"><span data-stu-id="26eb0-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="26eb0-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="26eb0-106">Description</span></span>

<span data-ttu-id="26eb0-107">Dado o `result` resultado, aplica a operação `zeroOp` com a sua entrada quando é igual a , e `zeroInput` `result` `Zero` aplica-se `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="26eb0-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="26eb0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="26eb0-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="26eb0-109">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="26eb0-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="26eb0-110">O resultado da medição utilizado para determinar se `zeroOp` ou `oneOp` é aplicado.</span><span class="sxs-lookup"><span data-stu-id="26eb0-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="26eb0-111">zeroOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="26eb0-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="26eb0-112">A operação contígua a aplicar quando `result == Zero` . .</span><span class="sxs-lookup"><span data-stu-id="26eb0-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="26eb0-113">zeroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="26eb0-113">zeroInput : 'T</span></span>

<span data-ttu-id="26eb0-114">A entrada a fornecer `zeroOp` quando `result == Zero` . .</span><span class="sxs-lookup"><span data-stu-id="26eb0-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="26eb0-115">oneOp : 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="26eb0-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="26eb0-116">A operação contígua a aplicar quando `result == One` . .</span><span class="sxs-lookup"><span data-stu-id="26eb0-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="26eb0-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="26eb0-117">oneInput : 'U</span></span>

<span data-ttu-id="26eb0-118">A entrada a fornecer `oneOp` quando `result == One` . .</span><span class="sxs-lookup"><span data-stu-id="26eb0-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26eb0-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26eb0-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="26eb0-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="26eb0-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26eb0-121">'T</span><span class="sxs-lookup"><span data-stu-id="26eb0-121">'T</span></span>

<span data-ttu-id="26eb0-122">O tipo de entrada da operação `zeroOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="26eb0-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="26eb0-123">'U</span><span class="sxs-lookup"><span data-stu-id="26eb0-123">'U</span></span>

<span data-ttu-id="26eb0-124">O tipo de entrada da operação `oneOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="26eb0-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="26eb0-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="26eb0-125">See Also</span></span>

- [<span data-ttu-id="26eb0-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="26eb0-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="26eb0-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="26eb0-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="26eb0-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="26eb0-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="26eb0-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="26eb0-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="26eb0-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="26eb0-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)