---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Aplicação OperaçãoIfElseR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 78c1cf23614fbb7c27122548de487c7350467948
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718157"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="fd399-102">Aplicação OperaçãoIfElseR</span><span class="sxs-lookup"><span data-stu-id="fd399-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="fd399-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fd399-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fd399-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd399-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd399-105">Aplica uma de duas operações, dependendo do valor de um resultado clássico.</span><span class="sxs-lookup"><span data-stu-id="fd399-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="fd399-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="fd399-106">Description</span></span>

<span data-ttu-id="fd399-107">Dado o `result` resultado, aplica a operação `zeroOp` com a sua entrada quando é igual a , e `zeroInput` `result` `Zero` aplica-se `oneOp(oneInput)` quando `result == One` .</span><span class="sxs-lookup"><span data-stu-id="fd399-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="fd399-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fd399-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="fd399-109">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="fd399-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="fd399-110">O resultado da medição utilizado para determinar se `zeroOp` ou `oneOp` é aplicado.</span><span class="sxs-lookup"><span data-stu-id="fd399-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="fd399-111">zeroOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fd399-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fd399-112">A operação a aplicar quando `result == Zero` . .</span><span class="sxs-lookup"><span data-stu-id="fd399-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="fd399-113">zeroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="fd399-113">zeroInput : 'T</span></span>

<span data-ttu-id="fd399-114">A entrada a fornecer `zeroOp` quando `result == Zero` . .</span><span class="sxs-lookup"><span data-stu-id="fd399-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="fd399-115">oneOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fd399-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fd399-116">A operação a aplicar quando `result == One` . .</span><span class="sxs-lookup"><span data-stu-id="fd399-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="fd399-117">oneInput : 'U</span><span class="sxs-lookup"><span data-stu-id="fd399-117">oneInput : 'U</span></span>

<span data-ttu-id="fd399-118">A entrada a fornecer `oneOp` quando `result == One` . .</span><span class="sxs-lookup"><span data-stu-id="fd399-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd399-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd399-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fd399-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="fd399-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fd399-121">'T</span><span class="sxs-lookup"><span data-stu-id="fd399-121">'T</span></span>

<span data-ttu-id="fd399-122">O tipo de entrada da operação `zeroOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fd399-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="fd399-123">'U</span><span class="sxs-lookup"><span data-stu-id="fd399-123">'U</span></span>

<span data-ttu-id="fd399-124">O tipo de entrada da operação `oneOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fd399-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd399-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fd399-125">See Also</span></span>

- [<span data-ttu-id="fd399-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="fd399-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="fd399-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="fd399-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="fd399-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="fd399-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="fd399-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="fd399-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="fd399-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="fd399-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)