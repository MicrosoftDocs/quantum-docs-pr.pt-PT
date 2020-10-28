---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: Aplicar operação ToHeadC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717247"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="33e27-102">Aplicar operação ToHeadC</span><span class="sxs-lookup"><span data-stu-id="33e27-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="33e27-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33e27-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33e27-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33e27-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33e27-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="33e27-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="33e27-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="33e27-106">Description</span></span>

<span data-ttu-id="33e27-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="33e27-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="33e27-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="33e27-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="33e27-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="33e27-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="33e27-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="33e27-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="33e27-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="33e27-111">targets : 'T[]</span></span>

<span data-ttu-id="33e27-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="33e27-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33e27-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33e27-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33e27-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="33e27-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33e27-115">'T</span><span class="sxs-lookup"><span data-stu-id="33e27-115">'T</span></span>

<span data-ttu-id="33e27-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="33e27-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="33e27-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="33e27-117">See Also</span></span>

- [<span data-ttu-id="33e27-118">Microsoft.Quantum.Canon.ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="33e27-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="33e27-119">Microsoft.Quantum.Canon.ApplyToHeada</span><span class="sxs-lookup"><span data-stu-id="33e27-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="33e27-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="33e27-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)