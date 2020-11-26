---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Função diagonal
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221543"
---
# <a name="diagonal-function"></a><span data-ttu-id="7ad3f-102">Função diagonal</span><span class="sxs-lookup"><span data-stu-id="7ad3f-102">Diagonal function</span></span>

<span data-ttu-id="7ad3f-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7ad3f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7ad3f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ad3f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ad3f-105">Devolve uma matriz de elementos diagonais de uma matriz bidimensional</span><span class="sxs-lookup"><span data-stu-id="7ad3f-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="7ad3f-106">Description</span><span class="sxs-lookup"><span data-stu-id="7ad3f-106">Description</span></span>

<span data-ttu-id="7ad3f-107">Se a matriz bidimensional não tiver uma forma quadrada, a diagonal sobre o mínimo sobre o número de linhas e colunas será devolvida.</span><span class="sxs-lookup"><span data-stu-id="7ad3f-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="7ad3f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7ad3f-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="7ad3f-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="7ad3f-109">matrix : 'T[][]</span></span>

<span data-ttu-id="7ad3f-110">Matriz 2-dimensional em ordem em linha</span><span class="sxs-lookup"><span data-stu-id="7ad3f-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="7ad3f-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="7ad3f-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7ad3f-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7ad3f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ad3f-113">'T</span><span class="sxs-lookup"><span data-stu-id="7ad3f-113">'T</span></span>

<span data-ttu-id="7ad3f-114">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="7ad3f-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ad3f-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7ad3f-115">See Also</span></span>

- [<span data-ttu-id="7ad3f-116">Microsoft.Quantum.Arrays.Transposto</span><span class="sxs-lookup"><span data-stu-id="7ad3f-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)