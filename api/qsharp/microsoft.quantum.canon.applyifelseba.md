---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: Aplicação OperaçãoIfElseBA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844992"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="5484f-102">Aplicação OperaçãoIfElseBA</span><span class="sxs-lookup"><span data-stu-id="5484f-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="5484f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5484f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5484f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5484f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5484f-105">Aplica uma de duas operações contíguas, dependendo do valor de uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="5484f-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="5484f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="5484f-106">Description</span></span>

<span data-ttu-id="5484f-107">Dado um `bit` pouco, aplica a operação `trueOp` com a sua entrada quando é , e `trueInput` `bit` `true` `falseOp(falseInput)` aplica-se quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="5484f-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="5484f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="5484f-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="5484f-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5484f-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5484f-110">O valor booleano usado para determinar se `trueOp` é ou `falseOp` não aplicado.</span><span class="sxs-lookup"><span data-stu-id="5484f-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj"></a><span data-ttu-id="5484f-111">trueOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="5484f-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5484f-112">A operação contígua a aplicar quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="5484f-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="5484f-113">verdadeiroInput : 'T</span><span class="sxs-lookup"><span data-stu-id="5484f-113">trueInput : 'T</span></span>

<span data-ttu-id="5484f-114">A entrada a fornecer `trueOp` quando `bit` é `true` .</span><span class="sxs-lookup"><span data-stu-id="5484f-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj"></a><span data-ttu-id="5484f-115">falseOp : 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="5484f-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5484f-116">A operação contígua a aplicar quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="5484f-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="5484f-117">falseInput : 'U</span><span class="sxs-lookup"><span data-stu-id="5484f-117">falseInput : 'U</span></span>

<span data-ttu-id="5484f-118">A entrada a fornecer `falseOp` quando `bit` é `false` .</span><span class="sxs-lookup"><span data-stu-id="5484f-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5484f-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5484f-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5484f-120">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5484f-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5484f-121">'T</span><span class="sxs-lookup"><span data-stu-id="5484f-121">'T</span></span>

<span data-ttu-id="5484f-122">O tipo de entrada da operação `trueOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="5484f-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="5484f-123">'U</span><span class="sxs-lookup"><span data-stu-id="5484f-123">'U</span></span>

<span data-ttu-id="5484f-124">O tipo de entrada da operação `falseOp` a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="5484f-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5484f-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5484f-125">See Also</span></span>

- [<span data-ttu-id="5484f-126">Microsoft.Quantum.Canon.ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="5484f-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="5484f-127">Microsoft.Quantum.Canon.ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="5484f-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="5484f-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="5484f-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="5484f-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="5484f-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="5484f-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="5484f-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)