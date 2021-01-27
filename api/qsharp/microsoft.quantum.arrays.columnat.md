---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Função ColumnAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846263"
---
# <a name="columnat-function"></a><span data-ttu-id="b62b4-102">Função ColumnAt</span><span class="sxs-lookup"><span data-stu-id="b62b4-102">ColumnAt function</span></span>

<span data-ttu-id="b62b4-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b62b4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b62b4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b62b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b62b4-105">Extrai uma coluna de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="b62b4-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b62b4-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b62b4-106">Description</span></span>

<span data-ttu-id="b62b4-107">Esta função extrai uma coluna numa matriz em ordem de linha.</span><span class="sxs-lookup"><span data-stu-id="b62b4-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="b62b4-108">Extrair uma linha de corrsponds para o acesso do elemento do primeiro índice e, portanto, não requer mais tratamento.</span><span class="sxs-lookup"><span data-stu-id="b62b4-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="b62b4-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="b62b4-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="b62b4-110">coluna : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b62b4-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b62b4-111">Coluna da matriz</span><span class="sxs-lookup"><span data-stu-id="b62b4-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="b62b4-112">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="b62b4-112">matrix : 'T[][]</span></span>

<span data-ttu-id="b62b4-113">Matriz 2-dimensional em ordem em linha</span><span class="sxs-lookup"><span data-stu-id="b62b4-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="b62b4-114">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="b62b4-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b62b4-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b62b4-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b62b4-116">'T</span><span class="sxs-lookup"><span data-stu-id="b62b4-116">'T</span></span>

<span data-ttu-id="b62b4-117">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="b62b4-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="b62b4-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b62b4-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="b62b4-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b62b4-119">See Also</span></span>

- [<span data-ttu-id="b62b4-120">Microsoft.Quantum.Arrays.Transposto</span><span class="sxs-lookup"><span data-stu-id="b62b4-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="b62b4-121">Microsoft.Quantum.Arrays.Diagonal</span><span class="sxs-lookup"><span data-stu-id="b62b4-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)