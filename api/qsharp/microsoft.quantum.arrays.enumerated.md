---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Função enumerada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848134"
---
# <a name="enumerated-function"></a><span data-ttu-id="9922c-102">Função enumerada</span><span class="sxs-lookup"><span data-stu-id="9922c-102">Enumerated function</span></span>

<span data-ttu-id="9922c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9922c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9922c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9922c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9922c-105">Dada uma matriz, devolve uma nova matriz contendo elementos da matriz original juntamente com os índices de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="9922c-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="9922c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9922c-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="9922c-107">matriz : 'TElement[]</span><span class="sxs-lookup"><span data-stu-id="9922c-107">array : 'TElement[]</span></span>

<span data-ttu-id="9922c-108">Uma matriz cujos elementos devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="9922c-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="9922c-109">Saída :[(Int](xref:microsoft.quantum.lang-ref.int)'TElement)[]</span><span class="sxs-lookup"><span data-stu-id="9922c-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="9922c-110">Uma nova matriz contendo elementos da matriz original juntamente com os seus índices.</span><span class="sxs-lookup"><span data-stu-id="9922c-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9922c-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9922c-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="9922c-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="9922c-112">'TElement</span></span>

<span data-ttu-id="9922c-113">O tipo de elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="9922c-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="9922c-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9922c-114">Example</span></span>

<span data-ttu-id="9922c-115">Os `for` seguintes ciclos são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="9922c-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```