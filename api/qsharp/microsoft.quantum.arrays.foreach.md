---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719206"
---
# <a name="foreach-operation"></a><span data-ttu-id="a4dfa-102">ForEach operação</span><span class="sxs-lookup"><span data-stu-id="a4dfa-102">ForEach operation</span></span>

<span data-ttu-id="a4dfa-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a4dfa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a4dfa-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4dfa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4dfa-105">Dada uma matriz e uma operação que é definida para os elementos da matriz, devolve uma nova matriz que consiste nas imagens da matriz original no âmbito da operação.</span><span class="sxs-lookup"><span data-stu-id="a4dfa-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="a4dfa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a4dfa-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="a4dfa-107">ação : 'T => 'U</span><span class="sxs-lookup"><span data-stu-id="a4dfa-107">action : 'T => 'U</span></span> 

<span data-ttu-id="a4dfa-108">Uma operação `'T` `'U` a partir daí é aplicada a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="a4dfa-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="a4dfa-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="a4dfa-109">array : 'T[]</span></span>

<span data-ttu-id="a4dfa-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="a4dfa-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="a4dfa-111">Saída : 'U].</span><span class="sxs-lookup"><span data-stu-id="a4dfa-111">Output : 'U[]</span></span>

<span data-ttu-id="a4dfa-112">Uma série `'U[]` de elementos que são mapeados pela `action` operação.</span><span class="sxs-lookup"><span data-stu-id="a4dfa-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a4dfa-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a4dfa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a4dfa-114">'T</span><span class="sxs-lookup"><span data-stu-id="a4dfa-114">'T</span></span>

<span data-ttu-id="a4dfa-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="a4dfa-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="a4dfa-116">'U</span><span class="sxs-lookup"><span data-stu-id="a4dfa-116">'U</span></span>

<span data-ttu-id="a4dfa-117">O tipo de resultado da `action` operação.</span><span class="sxs-lookup"><span data-stu-id="a4dfa-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4dfa-118">Observações</span><span class="sxs-lookup"><span data-stu-id="a4dfa-118">Remarks</span></span>

<span data-ttu-id="a4dfa-119">A operação é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma operação `action : 'T -> 'U` podemos mapear os elementos da matriz e produzir uma nova matriz de tipo `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="a4dfa-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>