---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Aplicação OperaçãoToElementA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208878"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="09b36-102">Aplicação OperaçãoToElementA</span><span class="sxs-lookup"><span data-stu-id="09b36-102">ApplyToElementA operation</span></span>

<span data-ttu-id="09b36-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09b36-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09b36-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09b36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09b36-105">Aplica uma operação a um determinado elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="09b36-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="09b36-106">Description</span><span class="sxs-lookup"><span data-stu-id="09b36-106">Description</span></span>

<span data-ttu-id="09b36-107">Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="09b36-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="09b36-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="09b36-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="09b36-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="09b36-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="09b36-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="09b36-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="09b36-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09b36-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09b36-112">Um índice na matriz de alvos.</span><span class="sxs-lookup"><span data-stu-id="09b36-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="09b36-113">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="09b36-113">targets : 'T[]</span></span>

<span data-ttu-id="09b36-114">Uma série de possíveis alvos para `op` .</span><span class="sxs-lookup"><span data-stu-id="09b36-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09b36-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09b36-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="09b36-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="09b36-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09b36-117">'T</span><span class="sxs-lookup"><span data-stu-id="09b36-117">'T</span></span>

<span data-ttu-id="09b36-118">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="09b36-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b36-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="09b36-119">See Also</span></span>

- [<span data-ttu-id="09b36-120">Microsoft.Quantum.Canon.ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="09b36-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="09b36-121">Microsoft.Quantum.Canon.ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="09b36-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="09b36-122">Microsoft.Quantum.Canon.ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="09b36-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)