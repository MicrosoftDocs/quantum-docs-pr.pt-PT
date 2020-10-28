---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: Aplicação OperaçãoIfElseB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718222"
---
# <a name="applyifelseb-operation"></a><span data-ttu-id="97b24-102">Aplicação OperaçãoIfElseB</span><span class="sxs-lookup"><span data-stu-id="97b24-102">ApplyIfElseB operation</span></span>

<span data-ttu-id="97b24-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="97b24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="97b24-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97b24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97b24-105">Aplica uma de duas operações, dependendo do valor de um pouco clássico.</span><span class="sxs-lookup"><span data-stu-id="97b24-105">Applies one of two operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="97b24-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="97b24-106">Description</span></span>

<span data-ttu-id="97b24-107">Dado um `bit` pouco, aplica a operação `trueOp` com a sua entrada quando é , e `trueInput` `bit` `true` `falseOp(falseInput)` aplica-se quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="97b24-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="97b24-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="97b24-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="97b24-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="97b24-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="97b24-110">O valor booleano usado para determinar se `trueOp` é ou `falseOp` não aplicado.</span><span class="sxs-lookup"><span data-stu-id="97b24-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit"></a><span data-ttu-id="97b24-111">trueOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="97b24-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="97b24-112">A operação a aplicar quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="97b24-112">The operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="97b24-113">verdadeiroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="97b24-113">trueInput : 'T</span></span>

<span data-ttu-id="97b24-114">A entrada a fornecer `trueOp` quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="97b24-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit"></a><span data-ttu-id="97b24-115">falseOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="97b24-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="97b24-116">A operação a aplicar quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="97b24-116">The operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="97b24-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="97b24-117">falseInput : 'U</span></span>

<span data-ttu-id="97b24-118">A entrada a fornecer `falseOp` quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="97b24-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97b24-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97b24-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="97b24-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="97b24-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="97b24-121">'T</span><span class="sxs-lookup"><span data-stu-id="97b24-121">'T</span></span>

<span data-ttu-id="97b24-122">O tipo de entrada da operação `trueOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="97b24-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="97b24-123">'U</span><span class="sxs-lookup"><span data-stu-id="97b24-123">'U</span></span>

<span data-ttu-id="97b24-124">O tipo de entrada da operação `falseOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="97b24-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="97b24-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="97b24-125">See Also</span></span>

- [<span data-ttu-id="97b24-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="97b24-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="97b24-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="97b24-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="97b24-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="97b24-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="97b24-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="97b24-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="97b24-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="97b24-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)