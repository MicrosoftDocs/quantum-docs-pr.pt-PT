---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Aplicação OperaçãoIfZero
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718059"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="72426-102">Aplicação OperaçãoIfZero</span><span class="sxs-lookup"><span data-stu-id="72426-102">ApplyIfZero operation</span></span>

<span data-ttu-id="72426-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72426-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72426-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72426-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72426-105">Aplica uma operação condicionada a um resultado clássico sendo zero.</span><span class="sxs-lookup"><span data-stu-id="72426-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="72426-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="72426-106">Description</span></span>

<span data-ttu-id="72426-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="72426-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="72426-108">Se, `One` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="72426-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="72426-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="72426-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="72426-110">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="72426-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="72426-111">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="72426-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="72426-112">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="72426-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="72426-113">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="72426-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="72426-114">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="72426-114">target : 'T</span></span>

<span data-ttu-id="72426-115">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="72426-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72426-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72426-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72426-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="72426-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72426-118">'T</span><span class="sxs-lookup"><span data-stu-id="72426-118">'T</span></span>

<span data-ttu-id="72426-119">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="72426-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="72426-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="72426-120">See Also</span></span>

- [<span data-ttu-id="72426-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="72426-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="72426-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="72426-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="72426-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="72426-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)