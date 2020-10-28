---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Função IndexRange
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719147"
---
# <a name="indexrange-function"></a><span data-ttu-id="1269c-102">Função IndexRange</span><span class="sxs-lookup"><span data-stu-id="1269c-102">IndexRange function</span></span>

<span data-ttu-id="1269c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1269c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1269c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1269c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1269c-105">Dada uma matriz, devolve um intervalo sobre os índices dessa matriz, adequado para ser utilizado em loop.</span><span class="sxs-lookup"><span data-stu-id="1269c-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="1269c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1269c-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="1269c-107">matriz : 'TElement[]</span><span class="sxs-lookup"><span data-stu-id="1269c-107">array : 'TElement[]</span></span>

<span data-ttu-id="1269c-108">Uma matriz para a qual uma série de índices deve ser devolvida.</span><span class="sxs-lookup"><span data-stu-id="1269c-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="1269c-109">Saída : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="1269c-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="1269c-110">Um alcance sobre todos os índices da matriz.</span><span class="sxs-lookup"><span data-stu-id="1269c-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1269c-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1269c-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="1269c-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="1269c-112">'TElement</span></span>

<span data-ttu-id="1269c-113">O tipo de elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="1269c-113">The type of elements of the array.</span></span>