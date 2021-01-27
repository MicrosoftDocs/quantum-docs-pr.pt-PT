---
uid: Microsoft.Quantum.Arrays.Transposed
title: Função transposta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850938"
---
# <a name="transposed-function"></a><span data-ttu-id="60059-102">Função transposta</span><span class="sxs-lookup"><span data-stu-id="60059-102">Transposed function</span></span>

<span data-ttu-id="60059-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60059-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60059-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60059-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60059-105">Devolve a transposição de uma matriz representada como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="60059-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="60059-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="60059-106">Description</span></span>

<span data-ttu-id="60059-107">Insira como uma matriz de $r \vezes c$ com linhas de $r$ e colunas de $c$.</span><span class="sxs-lookup"><span data-stu-id="60059-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="60059-108">A matriz é baseada em linha, ou seja, `matrix[i][j]` acede ao elemento na linha $i$ e coluna $j$.</span><span class="sxs-lookup"><span data-stu-id="60059-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="60059-109">Esta função devolve a matriz de $c \vezes r$ que é a transposição da matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="60059-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="60059-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="60059-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="60059-111">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="60059-111">matrix : 'T[][]</span></span>

<span data-ttu-id="60059-112">$r baseada em linha \vezes c$ matriz</span><span class="sxs-lookup"><span data-stu-id="60059-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="60059-113">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="60059-113">Output : 'T[][]</span></span>

<span data-ttu-id="60059-114">Transposto $c \times r$ matriz</span><span class="sxs-lookup"><span data-stu-id="60059-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60059-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="60059-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60059-116">'T</span><span class="sxs-lookup"><span data-stu-id="60059-116">'T</span></span>

<span data-ttu-id="60059-117">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="60059-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="60059-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="60059-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```