---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Aplicar operação ToHeadC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208606"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="c69c1-102">Aplicar operação ToHeadC</span><span class="sxs-lookup"><span data-stu-id="c69c1-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="c69c1-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c69c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c69c1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c69c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c69c1-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="c69c1-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="c69c1-106">Description</span><span class="sxs-lookup"><span data-stu-id="c69c1-106">Description</span></span>

<span data-ttu-id="c69c1-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c69c1-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c69c1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c69c1-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="c69c1-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="c69c1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c69c1-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="c69c1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c69c1-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="c69c1-111">targets : 'T[]</span></span>

<span data-ttu-id="c69c1-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="c69c1-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c69c1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c69c1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c69c1-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c69c1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c69c1-115">'T</span><span class="sxs-lookup"><span data-stu-id="c69c1-115">'T</span></span>

<span data-ttu-id="c69c1-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="c69c1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c69c1-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c69c1-117">See Also</span></span>

- [<span data-ttu-id="c69c1-118">Microsoft.Quantum.Canon.ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c69c1-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c69c1-119">Microsoft.Quantum.Canon.ApplyToHeada</span><span class="sxs-lookup"><span data-stu-id="c69c1-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="c69c1-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="c69c1-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)