---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Aplicação OperaçãoIfZeroA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718056"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="50405-102">Aplicação OperaçãoIfZeroA</span><span class="sxs-lookup"><span data-stu-id="50405-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="50405-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="50405-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="50405-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50405-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50405-105">Aplica uma operação contígua condicionada a um valor de resultado clássico sendo zero.</span><span class="sxs-lookup"><span data-stu-id="50405-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="50405-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="50405-106">Description</span></span>

<span data-ttu-id="50405-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="50405-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="50405-108">Se, `One` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="50405-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="50405-109">O `A` sufixo indica que a operação a aplicar é adjacente.</span><span class="sxs-lookup"><span data-stu-id="50405-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="50405-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="50405-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="50405-111">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="50405-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="50405-112">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="50405-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="50405-113">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="50405-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="50405-114">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="50405-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="50405-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="50405-115">target : 'T</span></span>

<span data-ttu-id="50405-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="50405-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50405-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50405-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="50405-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="50405-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50405-119">'T</span><span class="sxs-lookup"><span data-stu-id="50405-119">'T</span></span>

<span data-ttu-id="50405-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="50405-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="50405-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="50405-121">See Also</span></span>

- [<span data-ttu-id="50405-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="50405-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="50405-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="50405-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="50405-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="50405-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)