---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Função SquareArrayFact
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220200"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="55b08-102">Função SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="55b08-102">SquareArrayFact function</span></span>

<span data-ttu-id="55b08-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="55b08-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="55b08-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55b08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55b08-105">Representa uma condição de que uma matriz bidimensional tem uma forma quadrada</span><span class="sxs-lookup"><span data-stu-id="55b08-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="55b08-106">Description</span><span class="sxs-lookup"><span data-stu-id="55b08-106">Description</span></span>

<span data-ttu-id="55b08-107">Esta função afirma que cada linha de uma matriz tem tantos elementos como existem linhas (elementos) na matriz.</span><span class="sxs-lookup"><span data-stu-id="55b08-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="55b08-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="55b08-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="55b08-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="55b08-109">array : 'T[][]</span></span>

<span data-ttu-id="55b08-110">Uma matriz bidimensional de elementos</span><span class="sxs-lookup"><span data-stu-id="55b08-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="55b08-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="55b08-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="55b08-112">Uma mensagem a ser impressa se a matriz não é uma matriz quadrada</span><span class="sxs-lookup"><span data-stu-id="55b08-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="55b08-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55b08-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55b08-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="55b08-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55b08-115">'T</span><span class="sxs-lookup"><span data-stu-id="55b08-115">'T</span></span>

<span data-ttu-id="55b08-116">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="55b08-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="55b08-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="55b08-117">See Also</span></span>

- [<span data-ttu-id="55b08-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="55b08-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)