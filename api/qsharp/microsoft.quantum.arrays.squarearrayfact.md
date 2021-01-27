---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Função SquareArrayFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850972"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="661cd-102">Função SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="661cd-102">SquareArrayFact function</span></span>

<span data-ttu-id="661cd-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="661cd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="661cd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="661cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="661cd-105">Representa uma condição de que uma matriz bidimensional tem uma forma quadrada</span><span class="sxs-lookup"><span data-stu-id="661cd-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="661cd-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="661cd-106">Description</span></span>

<span data-ttu-id="661cd-107">Esta função afirma que cada linha de uma matriz tem tantos elementos como existem linhas (elementos) na matriz.</span><span class="sxs-lookup"><span data-stu-id="661cd-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="661cd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="661cd-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="661cd-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="661cd-109">array : 'T[][]</span></span>

<span data-ttu-id="661cd-110">Uma matriz bidimensional de elementos</span><span class="sxs-lookup"><span data-stu-id="661cd-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="661cd-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="661cd-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="661cd-112">Uma mensagem a ser impressa se a matriz não é uma matriz quadrada</span><span class="sxs-lookup"><span data-stu-id="661cd-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="661cd-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="661cd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="661cd-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="661cd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="661cd-115">'T</span><span class="sxs-lookup"><span data-stu-id="661cd-115">'T</span></span>

<span data-ttu-id="661cd-116">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="661cd-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="661cd-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="661cd-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="661cd-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="661cd-118">See Also</span></span>

- [<span data-ttu-id="661cd-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="661cd-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)