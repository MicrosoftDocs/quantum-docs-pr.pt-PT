---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Aplicação OperaçãoToElementCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208861"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="096a0-102">Aplicação OperaçãoToElementCA</span><span class="sxs-lookup"><span data-stu-id="096a0-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="096a0-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="096a0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="096a0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="096a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="096a0-105">Aplica uma operação a um determinado elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="096a0-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="096a0-106">Description</span><span class="sxs-lookup"><span data-stu-id="096a0-106">Description</span></span>

<span data-ttu-id="096a0-107">Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="096a0-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="096a0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="096a0-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="096a0-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="096a0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="096a0-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="096a0-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="096a0-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="096a0-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="096a0-112">Um índice na matriz de alvos.</span><span class="sxs-lookup"><span data-stu-id="096a0-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="096a0-113">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="096a0-113">targets : 'T[]</span></span>

<span data-ttu-id="096a0-114">Uma série de possíveis alvos para `op` .</span><span class="sxs-lookup"><span data-stu-id="096a0-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="096a0-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="096a0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="096a0-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="096a0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="096a0-117">'T</span><span class="sxs-lookup"><span data-stu-id="096a0-117">'T</span></span>

<span data-ttu-id="096a0-118">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="096a0-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="096a0-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="096a0-119">See Also</span></span>

- [<span data-ttu-id="096a0-120">Microsoft.Quantum.Canon.ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="096a0-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="096a0-121">Microsoft.Quantum.Canon.ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="096a0-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="096a0-122">Microsoft.Quantum.Canon.ApplyToElementa</span><span class="sxs-lookup"><span data-stu-id="096a0-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)