---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Função enumerada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221424"
---
# <a name="enumerated-function"></a><span data-ttu-id="3b53b-102">Função enumerada</span><span class="sxs-lookup"><span data-stu-id="3b53b-102">Enumerated function</span></span>

<span data-ttu-id="3b53b-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3b53b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3b53b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b53b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b53b-105">Dada uma matriz, devolve uma nova matriz contendo elementos da matriz original juntamente com os índices de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="3b53b-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="3b53b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3b53b-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="3b53b-107">matriz : 'TElement[]</span><span class="sxs-lookup"><span data-stu-id="3b53b-107">array : 'TElement[]</span></span>

<span data-ttu-id="3b53b-108">Uma matriz cujos elementos devem ser enumerados.</span><span class="sxs-lookup"><span data-stu-id="3b53b-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="3b53b-109">Saída :[(Int](xref:microsoft.quantum.lang-ref.int)'TElement)[]</span><span class="sxs-lookup"><span data-stu-id="3b53b-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="3b53b-110">Uma nova matriz contendo elementos da matriz original juntamente com os seus índices.</span><span class="sxs-lookup"><span data-stu-id="3b53b-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3b53b-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="3b53b-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="3b53b-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="3b53b-112">'TElement</span></span>

<span data-ttu-id="3b53b-113">O tipo de elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="3b53b-113">The type of elements of the array.</span></span>