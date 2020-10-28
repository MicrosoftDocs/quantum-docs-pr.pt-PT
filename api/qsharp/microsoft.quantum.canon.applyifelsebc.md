---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: Aplicação OperaçãoIfElseBC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 032d92484dc96481cb981d9d8acfeed248a9116d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718211"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="42334-102">Aplicação OperaçãoIfElseBC</span><span class="sxs-lookup"><span data-stu-id="42334-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="42334-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42334-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42334-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42334-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42334-105">Aplica uma de duas operações controláveis, dependendo do valor de uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="42334-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="42334-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="42334-106">Description</span></span>

<span data-ttu-id="42334-107">Dado um `bit` pouco, aplica a operação `trueOp` com a sua entrada quando é , e `trueInput` `bit` `true` `falseOp(falseInput)` aplica-se quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="42334-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="42334-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="42334-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="42334-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="42334-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="42334-110">O valor booleano usado para determinar se `trueOp` é ou `falseOp` não aplicado.</span><span class="sxs-lookup"><span data-stu-id="42334-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-ctl"></a><span data-ttu-id="42334-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="42334-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="42334-112">A operação controlável a aplicar quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="42334-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="42334-113">verdadeiroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="42334-113">trueInput : 'T</span></span>

<span data-ttu-id="42334-114">A entrada a fornecer `trueOp` quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="42334-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-ctl"></a><span data-ttu-id="42334-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="42334-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="42334-116">A operação controlável a aplicar quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="42334-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="42334-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="42334-117">falseInput : 'U</span></span>

<span data-ttu-id="42334-118">A entrada a fornecer `falseOp` quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="42334-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42334-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42334-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="42334-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="42334-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="42334-121">'T</span><span class="sxs-lookup"><span data-stu-id="42334-121">'T</span></span>

<span data-ttu-id="42334-122">O tipo de entrada da operação `trueOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="42334-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="42334-123">'U</span><span class="sxs-lookup"><span data-stu-id="42334-123">'U</span></span>

<span data-ttu-id="42334-124">O tipo de entrada da operação `falseOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="42334-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="42334-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="42334-125">See Also</span></span>

- [<span data-ttu-id="42334-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="42334-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="42334-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="42334-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="42334-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="42334-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="42334-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="42334-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="42334-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="42334-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)