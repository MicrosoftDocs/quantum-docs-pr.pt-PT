---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Aplicação Operação ToHeadCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: f28cff599e06090145fac860dbaf8274c966f80a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208555"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="ad14d-102">Aplicação Operação ToHeadCA</span><span class="sxs-lookup"><span data-stu-id="ad14d-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="ad14d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad14d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad14d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad14d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad14d-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="ad14d-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ad14d-106">Description</span><span class="sxs-lookup"><span data-stu-id="ad14d-106">Description</span></span>

<span data-ttu-id="ad14d-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ad14d-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ad14d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ad14d-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ad14d-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="ad14d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ad14d-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="ad14d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ad14d-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="ad14d-111">targets : 'T[]</span></span>

<span data-ttu-id="ad14d-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="ad14d-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad14d-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad14d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ad14d-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ad14d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad14d-115">'T</span><span class="sxs-lookup"><span data-stu-id="ad14d-115">'T</span></span>

<span data-ttu-id="ad14d-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ad14d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad14d-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ad14d-117">See Also</span></span>

- [<span data-ttu-id="ad14d-118">Microsoft.Quantum.Canon.ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="ad14d-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="ad14d-119">Microsoft.Quantum.Canon.ApplyToHeada</span><span class="sxs-lookup"><span data-stu-id="ad14d-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="ad14d-120">Microsoft.Quantum.Canon.ApplyToHeadc</span><span class="sxs-lookup"><span data-stu-id="ad14d-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)