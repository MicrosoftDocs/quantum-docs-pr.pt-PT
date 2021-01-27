---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Aplicação OperaçãoToElementA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850756"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="bec62-102">Aplicação OperaçãoToElementA</span><span class="sxs-lookup"><span data-stu-id="bec62-102">ApplyToElementA operation</span></span>

<span data-ttu-id="bec62-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bec62-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bec62-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bec62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bec62-105">Aplica uma operação a um determinado elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="bec62-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="bec62-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="bec62-106">Description</span></span>

<span data-ttu-id="bec62-107">Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="bec62-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="bec62-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="bec62-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="bec62-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="bec62-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bec62-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="bec62-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="bec62-111">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bec62-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bec62-112">Um índice na matriz de alvos.</span><span class="sxs-lookup"><span data-stu-id="bec62-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bec62-113">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="bec62-113">targets : 'T[]</span></span>

<span data-ttu-id="bec62-114">Uma série de possíveis alvos para `op` .</span><span class="sxs-lookup"><span data-stu-id="bec62-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bec62-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bec62-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bec62-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bec62-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bec62-117">'T</span><span class="sxs-lookup"><span data-stu-id="bec62-117">'T</span></span>

<span data-ttu-id="bec62-118">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="bec62-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bec62-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bec62-119">See Also</span></span>

- [<span data-ttu-id="bec62-120">Microsoft.Quantum.Canon.ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="bec62-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="bec62-121">Microsoft.Quantum.Canon.ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="bec62-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="bec62-122">Microsoft.Quantum.Canon.ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="bec62-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)