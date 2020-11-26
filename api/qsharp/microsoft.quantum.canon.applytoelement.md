---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: Aplicação OperaçãoToElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8cbc42a1c43b4c9a037729671eb3c82d365af580
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217632"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="af1dc-102">Aplicação OperaçãoToElement</span><span class="sxs-lookup"><span data-stu-id="af1dc-102">ApplyToElement operation</span></span>

<span data-ttu-id="af1dc-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="af1dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="af1dc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af1dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af1dc-105">Aplica uma operação a um determinado elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="af1dc-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="af1dc-106">Description</span><span class="sxs-lookup"><span data-stu-id="af1dc-106">Description</span></span>

<span data-ttu-id="af1dc-107">Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="af1dc-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="af1dc-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="af1dc-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="af1dc-109">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="af1dc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="af1dc-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="af1dc-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="af1dc-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="af1dc-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="af1dc-112">Um índice na matriz de alvos.</span><span class="sxs-lookup"><span data-stu-id="af1dc-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="af1dc-113">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="af1dc-113">targets : 'T[]</span></span>

<span data-ttu-id="af1dc-114">Uma série de possíveis alvos para `op` .</span><span class="sxs-lookup"><span data-stu-id="af1dc-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af1dc-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af1dc-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="af1dc-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="af1dc-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af1dc-117">'T</span><span class="sxs-lookup"><span data-stu-id="af1dc-117">'T</span></span>

<span data-ttu-id="af1dc-118">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="af1dc-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="af1dc-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="af1dc-119">See Also</span></span>

- [<span data-ttu-id="af1dc-120">Microsoft.Quantum.Canon.ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="af1dc-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="af1dc-121">Microsoft.Quantum.Canon.ApplyToElementa</span><span class="sxs-lookup"><span data-stu-id="af1dc-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="af1dc-122">Microsoft.Quantum.Canon.ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="af1dc-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)