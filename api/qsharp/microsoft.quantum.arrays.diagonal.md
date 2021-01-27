---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Função diagonal
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842835"
---
# <a name="diagonal-function"></a><span data-ttu-id="2bb11-102">Função diagonal</span><span class="sxs-lookup"><span data-stu-id="2bb11-102">Diagonal function</span></span>

<span data-ttu-id="2bb11-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2bb11-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2bb11-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bb11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bb11-105">Devolve uma matriz de elementos diagonais de uma matriz bidimensional</span><span class="sxs-lookup"><span data-stu-id="2bb11-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2bb11-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="2bb11-106">Description</span></span>

<span data-ttu-id="2bb11-107">Se a matriz bidimensional não tiver uma forma quadrada, a diagonal sobre o mínimo sobre o número de linhas e colunas será devolvida.</span><span class="sxs-lookup"><span data-stu-id="2bb11-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="2bb11-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2bb11-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="2bb11-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="2bb11-109">matrix : 'T[][]</span></span>

<span data-ttu-id="2bb11-110">Matriz 2-dimensional em ordem em linha</span><span class="sxs-lookup"><span data-stu-id="2bb11-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="2bb11-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="2bb11-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2bb11-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2bb11-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2bb11-113">'T</span><span class="sxs-lookup"><span data-stu-id="2bb11-113">'T</span></span>

<span data-ttu-id="2bb11-114">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="2bb11-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="2bb11-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2bb11-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="2bb11-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2bb11-116">See Also</span></span>

- [<span data-ttu-id="2bb11-117">Microsoft.Quantum.Arrays.Transposto</span><span class="sxs-lookup"><span data-stu-id="2bb11-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)