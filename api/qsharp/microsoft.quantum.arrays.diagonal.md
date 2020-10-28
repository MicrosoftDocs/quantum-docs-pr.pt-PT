---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Função diagonal
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719386"
---
# <a name="diagonal-function"></a><span data-ttu-id="b598e-102">Função diagonal</span><span class="sxs-lookup"><span data-stu-id="b598e-102">Diagonal function</span></span>

<span data-ttu-id="b598e-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b598e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b598e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b598e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b598e-105">Devolve uma matriz de elementos diagonais de uma matriz bidimensional</span><span class="sxs-lookup"><span data-stu-id="b598e-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b598e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b598e-106">Description</span></span>

<span data-ttu-id="b598e-107">Se a matriz bidimensional não tiver uma forma quadrada, a diagonal sobre o mínimo sobre o número de linhas e colunas será devolvida.</span><span class="sxs-lookup"><span data-stu-id="b598e-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="b598e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b598e-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="b598e-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="b598e-109">matrix : 'T[][]</span></span>

<span data-ttu-id="b598e-110">Matriz 2-dimensional em ordem em linha</span><span class="sxs-lookup"><span data-stu-id="b598e-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="b598e-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="b598e-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b598e-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b598e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b598e-113">'T</span><span class="sxs-lookup"><span data-stu-id="b598e-113">'T</span></span>

<span data-ttu-id="b598e-114">O tipo de cada elemento de `matrix` .</span><span class="sxs-lookup"><span data-stu-id="b598e-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b598e-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b598e-115">See Also</span></span>

- [<span data-ttu-id="b598e-116">Microsoft.Quantum.Arrays.Transposto</span><span class="sxs-lookup"><span data-stu-id="b598e-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)