---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: Aplicação OperaçãoIfElseBCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718196"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="836de-102">Aplicação OperaçãoIfElseBCA</span><span class="sxs-lookup"><span data-stu-id="836de-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="836de-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="836de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="836de-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="836de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="836de-105">Aplica uma de duas operações unitárias, dependendo do valor de uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="836de-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="836de-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="836de-106">Description</span></span>

<span data-ttu-id="836de-107">Dado um `bit` pouco, aplica a operação `trueOp` com a sua entrada quando é , e `trueInput` `bit` `true` `falseOp(falseInput)` aplica-se quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="836de-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="836de-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="836de-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="836de-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="836de-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="836de-110">O valor booleano usado para determinar se `trueOp` é ou `falseOp` não aplicado.</span><span class="sxs-lookup"><span data-stu-id="836de-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj--ctl"></a><span data-ttu-id="836de-111">trueOp : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="836de-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="836de-112">A operação unitária a aplicar quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="836de-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="836de-113">verdadeiroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="836de-113">trueInput : 'T</span></span>

<span data-ttu-id="836de-114">A entrada a fornecer `trueOp` quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="836de-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj--ctl"></a><span data-ttu-id="836de-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="836de-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="836de-116">A operação unitária a aplicar quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="836de-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="836de-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="836de-117">falseInput : 'U</span></span>

<span data-ttu-id="836de-118">A entrada a fornecer `falseOp` quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="836de-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="836de-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="836de-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="836de-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="836de-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="836de-121">'T</span><span class="sxs-lookup"><span data-stu-id="836de-121">'T</span></span>

<span data-ttu-id="836de-122">O tipo de entrada da operação `trueOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="836de-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="836de-123">'U</span><span class="sxs-lookup"><span data-stu-id="836de-123">'U</span></span>

<span data-ttu-id="836de-124">O tipo de entrada da operação `falseOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="836de-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="836de-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="836de-125">See Also</span></span>

- [<span data-ttu-id="836de-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="836de-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="836de-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="836de-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="836de-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="836de-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="836de-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="836de-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="836de-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="836de-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)