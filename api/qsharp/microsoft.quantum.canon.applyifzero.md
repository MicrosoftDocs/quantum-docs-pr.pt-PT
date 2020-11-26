---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: Aplicação OperaçãoIfZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3b14ef8a1aa736fe096a21fe51be5a7c5bb1d09d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209439"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="65d49-102">Aplicação OperaçãoIfZero</span><span class="sxs-lookup"><span data-stu-id="65d49-102">ApplyIfZero operation</span></span>

<span data-ttu-id="65d49-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65d49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65d49-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65d49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65d49-105">Aplica uma operação condicionada a um resultado clássico sendo zero.</span><span class="sxs-lookup"><span data-stu-id="65d49-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="65d49-106">Description</span><span class="sxs-lookup"><span data-stu-id="65d49-106">Description</span></span>

<span data-ttu-id="65d49-107">Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="65d49-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="65d49-108">Se, `One` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="65d49-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="65d49-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="65d49-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="65d49-110">resultado : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="65d49-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="65d49-111">Um resultado de medição que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="65d49-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="65d49-112">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="65d49-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="65d49-113">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="65d49-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="65d49-114">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="65d49-114">target : 'T</span></span>

<span data-ttu-id="65d49-115">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="65d49-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65d49-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65d49-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65d49-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="65d49-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65d49-118">'T</span><span class="sxs-lookup"><span data-stu-id="65d49-118">'T</span></span>

<span data-ttu-id="65d49-119">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="65d49-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="65d49-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="65d49-120">See Also</span></span>

- [<span data-ttu-id="65d49-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="65d49-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="65d49-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="65d49-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="65d49-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="65d49-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)