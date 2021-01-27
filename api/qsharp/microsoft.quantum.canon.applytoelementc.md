---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Aplicação OperaçãoElementC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850752"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="4b8d5-102">Aplicação OperaçãoElementC</span><span class="sxs-lookup"><span data-stu-id="4b8d5-102">ApplyToElementC operation</span></span>

<span data-ttu-id="4b8d5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b8d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b8d5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b8d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b8d5-105">Aplica uma operação a um determinado elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="4b8d5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b8d5-106">Description</span></span>

<span data-ttu-id="4b8d5-107">Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="4b8d5-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="4b8d5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b8d5-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="4b8d5-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="4b8d5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4b8d5-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="4b8d5-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b8d5-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b8d5-112">Um índice na matriz de alvos.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4b8d5-113">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4b8d5-113">targets : 'T[]</span></span>

<span data-ttu-id="4b8d5-114">Uma série de possíveis alvos para `op` .</span><span class="sxs-lookup"><span data-stu-id="4b8d5-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b8d5-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b8d5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4b8d5-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4b8d5-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b8d5-117">'T</span><span class="sxs-lookup"><span data-stu-id="4b8d5-117">'T</span></span>

<span data-ttu-id="4b8d5-118">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b8d5-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4b8d5-119">See Also</span></span>

- [<span data-ttu-id="4b8d5-120">Microsoft.Quantum.Canon.ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="4b8d5-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="4b8d5-121">Microsoft.Quantum.Canon.ApplyToElementa</span><span class="sxs-lookup"><span data-stu-id="4b8d5-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="4b8d5-122">Microsoft.Quantum.Canon.ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="4b8d5-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)