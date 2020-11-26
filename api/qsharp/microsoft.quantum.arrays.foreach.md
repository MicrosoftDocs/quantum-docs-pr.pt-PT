---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221152"
---
# <a name="foreach-operation"></a><span data-ttu-id="4db21-102">ForEach operação</span><span class="sxs-lookup"><span data-stu-id="4db21-102">ForEach operation</span></span>

<span data-ttu-id="4db21-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4db21-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4db21-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4db21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4db21-105">Dada uma matriz e uma operação que é definida para os elementos da matriz, devolve uma nova matriz que consiste nas imagens da matriz original no âmbito da operação.</span><span class="sxs-lookup"><span data-stu-id="4db21-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="4db21-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4db21-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="4db21-107">ação : 'T => 'U</span><span class="sxs-lookup"><span data-stu-id="4db21-107">action : 'T => 'U</span></span> 

<span data-ttu-id="4db21-108">Uma operação `'T` `'U` a partir daí é aplicada a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="4db21-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="4db21-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4db21-109">array : 'T[]</span></span>

<span data-ttu-id="4db21-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="4db21-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="4db21-111">Saída : 'U].</span><span class="sxs-lookup"><span data-stu-id="4db21-111">Output : 'U[]</span></span>

<span data-ttu-id="4db21-112">Uma série `'U[]` de elementos que são mapeados pela `action` operação.</span><span class="sxs-lookup"><span data-stu-id="4db21-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4db21-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4db21-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4db21-114">'T</span><span class="sxs-lookup"><span data-stu-id="4db21-114">'T</span></span>

<span data-ttu-id="4db21-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="4db21-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="4db21-116">'U</span><span class="sxs-lookup"><span data-stu-id="4db21-116">'U</span></span>

<span data-ttu-id="4db21-117">O tipo de resultado da `action` operação.</span><span class="sxs-lookup"><span data-stu-id="4db21-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="4db21-118">Observações</span><span class="sxs-lookup"><span data-stu-id="4db21-118">Remarks</span></span>

<span data-ttu-id="4db21-119">A operação é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma operação `action : 'T -> 'U` podemos mapear os elementos da matriz e produzir uma nova matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="4db21-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>