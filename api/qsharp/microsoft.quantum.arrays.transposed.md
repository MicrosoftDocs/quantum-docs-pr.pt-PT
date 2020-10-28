---
uid: Microsoft.Quantum.Arrays.Transposed
title: Função transposta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718811"
---
# <a name="transposed-function"></a><span data-ttu-id="0f319-102">Função transposta</span><span class="sxs-lookup"><span data-stu-id="0f319-102">Transposed function</span></span>

<span data-ttu-id="0f319-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0f319-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0f319-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f319-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f319-105">Devolve a transposição de uma matriz representada como uma matriz.</span><span class="sxs-lookup"><span data-stu-id="0f319-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="0f319-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0f319-106">Description</span></span>

<span data-ttu-id="0f319-107">Insira como uma matriz de $r \vezes c$ com linhas de $r$ e colunas de $c$.</span><span class="sxs-lookup"><span data-stu-id="0f319-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="0f319-108">A matriz é baseada em linha, ou seja, `matrix[i][j]` acede ao elemento na linha $i$ e coluna $j$.</span><span class="sxs-lookup"><span data-stu-id="0f319-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="0f319-109">Esta função devolve a matriz de $c \vezes r$ que é a transposição da matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="0f319-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="0f319-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f319-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="0f319-111">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="0f319-111">matrix : 'T[][]</span></span>

<span data-ttu-id="0f319-112">$r baseada em linha \vezes c$ matriz</span><span class="sxs-lookup"><span data-stu-id="0f319-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="0f319-113">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="0f319-113">Output : 'T[][]</span></span>

<span data-ttu-id="0f319-114">Transposto $c \times r$ matriz</span><span class="sxs-lookup"><span data-stu-id="0f319-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f319-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0f319-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f319-116">'T</span><span class="sxs-lookup"><span data-stu-id="0f319-116">'T</span></span>

<span data-ttu-id="0f319-117">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="0f319-117">The type of each element of `matrix`.</span></span>