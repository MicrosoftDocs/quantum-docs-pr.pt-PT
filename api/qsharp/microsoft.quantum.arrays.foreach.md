---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848591"
---
# <a name="foreach-operation"></a><span data-ttu-id="bd027-102">ForEach operação</span><span class="sxs-lookup"><span data-stu-id="bd027-102">ForEach operation</span></span>

<span data-ttu-id="bd027-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bd027-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bd027-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd027-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd027-105">Dada uma matriz e uma operação que é definida para os elementos da matriz, devolve uma nova matriz que consiste nas imagens da matriz original no âmbito da operação.</span><span class="sxs-lookup"><span data-stu-id="bd027-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="bd027-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bd027-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="bd027-107">ação : 'T => 'U</span><span class="sxs-lookup"><span data-stu-id="bd027-107">action : 'T => 'U</span></span> 

<span data-ttu-id="bd027-108">Uma operação `'T` `'U` a partir daí é aplicada a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="bd027-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="bd027-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="bd027-109">array : 'T[]</span></span>

<span data-ttu-id="bd027-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="bd027-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="bd027-111">Saída : 'U].</span><span class="sxs-lookup"><span data-stu-id="bd027-111">Output : 'U[]</span></span>

<span data-ttu-id="bd027-112">Uma série `'U[]` de elementos que são mapeados pela `action` operação.</span><span class="sxs-lookup"><span data-stu-id="bd027-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd027-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bd027-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd027-114">'T</span><span class="sxs-lookup"><span data-stu-id="bd027-114">'T</span></span>

<span data-ttu-id="bd027-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="bd027-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="bd027-116">'U</span><span class="sxs-lookup"><span data-stu-id="bd027-116">'U</span></span>

<span data-ttu-id="bd027-117">O tipo de resultado da `action` operação.</span><span class="sxs-lookup"><span data-stu-id="bd027-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd027-118">Observações</span><span class="sxs-lookup"><span data-stu-id="bd027-118">Remarks</span></span>

<span data-ttu-id="bd027-119">A operação é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma operação `action : 'T -> 'U` podemos mapear os elementos da matriz e produzir uma nova matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="bd027-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>