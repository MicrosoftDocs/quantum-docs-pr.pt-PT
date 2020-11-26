---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Função ColumnAt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210105"
---
# <a name="columnat-function"></a><span data-ttu-id="2f210-102">Função ColumnAt</span><span class="sxs-lookup"><span data-stu-id="2f210-102">ColumnAt function</span></span>

<span data-ttu-id="2f210-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f210-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f210-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f210-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f210-105">Extrai uma coluna de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="2f210-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2f210-106">Description</span><span class="sxs-lookup"><span data-stu-id="2f210-106">Description</span></span>

<span data-ttu-id="2f210-107">Esta função extrai uma coluna numa matriz em ordem de linha.</span><span class="sxs-lookup"><span data-stu-id="2f210-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="2f210-108">Extrair uma linha de corrsponds para o acesso do elemento do primeiro índice e, portanto, não requer mais tratamento.</span><span class="sxs-lookup"><span data-stu-id="2f210-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="2f210-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="2f210-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="2f210-110">coluna : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f210-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f210-111">Coluna da matriz</span><span class="sxs-lookup"><span data-stu-id="2f210-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="2f210-112">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="2f210-112">matrix : 'T[][]</span></span>

<span data-ttu-id="2f210-113">Matriz 2-dimensional em ordem em linha</span><span class="sxs-lookup"><span data-stu-id="2f210-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="2f210-114">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="2f210-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f210-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2f210-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f210-116">'T</span><span class="sxs-lookup"><span data-stu-id="2f210-116">'T</span></span>

<span data-ttu-id="2f210-117">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="2f210-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f210-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2f210-118">See Also</span></span>

- [<span data-ttu-id="2f210-119">Microsoft.Quantum.Arrays.Transposto</span><span class="sxs-lookup"><span data-stu-id="2f210-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="2f210-120">Microsoft.Quantum.Arrays.Diagonal</span><span class="sxs-lookup"><span data-stu-id="2f210-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)