---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Aplicação OperaçãoToElementCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717443"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="f72c8-102">Aplicação OperaçãoToElementCA</span><span class="sxs-lookup"><span data-stu-id="f72c8-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="f72c8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f72c8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f72c8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f72c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f72c8-105">Aplica uma operação a um determinado elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="f72c8-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f72c8-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="f72c8-106">Description</span></span>

<span data-ttu-id="f72c8-107">Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="f72c8-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="f72c8-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f72c8-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="f72c8-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="f72c8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f72c8-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f72c8-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="f72c8-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f72c8-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f72c8-112">Um índice na matriz de alvos.</span><span class="sxs-lookup"><span data-stu-id="f72c8-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f72c8-113">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f72c8-113">targets : 'T[]</span></span>

<span data-ttu-id="f72c8-114">Uma série de possíveis alvos para `op` .</span><span class="sxs-lookup"><span data-stu-id="f72c8-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f72c8-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f72c8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f72c8-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f72c8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f72c8-117">'T</span><span class="sxs-lookup"><span data-stu-id="f72c8-117">'T</span></span>

<span data-ttu-id="f72c8-118">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f72c8-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f72c8-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f72c8-119">See Also</span></span>

- [<span data-ttu-id="f72c8-120">Microsoft.Quantum.Canon.ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="f72c8-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="f72c8-121">Microsoft.Quantum.Canon.ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="f72c8-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="f72c8-122">Microsoft.Quantum.Canon.ApplyToElementa</span><span class="sxs-lookup"><span data-stu-id="f72c8-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)