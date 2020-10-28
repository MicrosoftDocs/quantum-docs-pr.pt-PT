---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: AplicarIfOne
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718101"
---
# <a name="applyifone-operation"></a><span data-ttu-id="fcc23-102">AplicarIfOne</span><span class="sxs-lookup"><span data-stu-id="fcc23-102">ApplyIfOne operation</span></span>

<span data-ttu-id="fcc23-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fcc23-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fcc23-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcc23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcc23-105">Aplica uma operação condicionada a um valor de resultado clássico sendo um.</span><span class="sxs-lookup"><span data-stu-id="fcc23-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="fcc23-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="fcc23-106">Description</span></span>

<span data-ttu-id="fcc23-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="fcc23-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="fcc23-108">Se, `Zero` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="fcc23-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="fcc23-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="fcc23-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="fcc23-110">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="fcc23-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="fcc23-111">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="fcc23-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="fcc23-112">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fcc23-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fcc23-113">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fcc23-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="fcc23-114">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="fcc23-114">target : 'T</span></span>

<span data-ttu-id="fcc23-115">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="fcc23-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcc23-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcc23-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fcc23-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="fcc23-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fcc23-118">'T</span><span class="sxs-lookup"><span data-stu-id="fcc23-118">'T</span></span>

<span data-ttu-id="fcc23-119">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fcc23-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcc23-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fcc23-120">See Also</span></span>

- [<span data-ttu-id="fcc23-121">Microsoft.Quantum.Canon.ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="fcc23-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="fcc23-122">Microsoft.Quantum.Canon.ApplyIfOnea</span><span class="sxs-lookup"><span data-stu-id="fcc23-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="fcc23-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="fcc23-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)