---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Função IndexRange
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845786"
---
# <a name="indexrange-function"></a><span data-ttu-id="53072-102">Função IndexRange</span><span class="sxs-lookup"><span data-stu-id="53072-102">IndexRange function</span></span>

<span data-ttu-id="53072-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="53072-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="53072-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="53072-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="53072-105">Dada uma matriz, devolve um intervalo sobre os índices dessa matriz, adequado para ser utilizado em loop.</span><span class="sxs-lookup"><span data-stu-id="53072-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="53072-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="53072-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="53072-107">matriz : 'TElement[]</span><span class="sxs-lookup"><span data-stu-id="53072-107">array : 'TElement[]</span></span>

<span data-ttu-id="53072-108">Uma matriz para a qual uma série de índices deve ser devolvida.</span><span class="sxs-lookup"><span data-stu-id="53072-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="53072-109">Saída : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="53072-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="53072-110">Um alcance sobre todos os índices da matriz.</span><span class="sxs-lookup"><span data-stu-id="53072-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="53072-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="53072-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="53072-112">'TElement</span><span class="sxs-lookup"><span data-stu-id="53072-112">'TElement</span></span>

<span data-ttu-id="53072-113">O tipo de elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="53072-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="53072-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="53072-114">Example</span></span>

<span data-ttu-id="53072-115">Os `for` seguintes ciclos são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="53072-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```