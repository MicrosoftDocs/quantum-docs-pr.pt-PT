---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Aplicação Operação ToHeadCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717233"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="ea58a-102">Aplicação Operação ToHeadCA</span><span class="sxs-lookup"><span data-stu-id="ea58a-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="ea58a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea58a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea58a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea58a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea58a-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="ea58a-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ea58a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="ea58a-106">Description</span></span>

<span data-ttu-id="ea58a-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ea58a-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ea58a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ea58a-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="ea58a-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="ea58a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ea58a-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="ea58a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ea58a-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="ea58a-111">targets : 'T[]</span></span>

<span data-ttu-id="ea58a-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="ea58a-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea58a-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea58a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ea58a-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ea58a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea58a-115">'T</span><span class="sxs-lookup"><span data-stu-id="ea58a-115">'T</span></span>

<span data-ttu-id="ea58a-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="ea58a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea58a-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ea58a-117">See Also</span></span>

- [<span data-ttu-id="ea58a-118">Microsoft.Quantum.Canon.ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="ea58a-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="ea58a-119">Microsoft.Quantum.Canon.ApplyToHeada</span><span class="sxs-lookup"><span data-stu-id="ea58a-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="ea58a-120">Microsoft.Quantum.Canon.ApplyToHeadc</span><span class="sxs-lookup"><span data-stu-id="ea58a-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)