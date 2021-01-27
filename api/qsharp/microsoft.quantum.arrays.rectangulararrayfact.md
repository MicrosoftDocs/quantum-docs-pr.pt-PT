---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Função RectangularArrayFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845492"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="10ac1-102">Função RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="10ac1-102">RectangularArrayFact function</span></span>

<span data-ttu-id="10ac1-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="10ac1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="10ac1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10ac1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10ac1-105">Representa uma condição de que uma matriz bidimensional tem uma forma retangular</span><span class="sxs-lookup"><span data-stu-id="10ac1-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="10ac1-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="10ac1-106">Description</span></span>

<span data-ttu-id="10ac1-107">Esta função afirma que cada linha de uma matriz tem o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="10ac1-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="10ac1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="10ac1-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="10ac1-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="10ac1-109">array : 'T[][]</span></span>

<span data-ttu-id="10ac1-110">Uma matriz bidimensional de elementos</span><span class="sxs-lookup"><span data-stu-id="10ac1-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="10ac1-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="10ac1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="10ac1-112">Uma mensagem a ser impressa se a matriz não for uma matriz retangular</span><span class="sxs-lookup"><span data-stu-id="10ac1-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="10ac1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10ac1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="10ac1-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="10ac1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="10ac1-115">'T</span><span class="sxs-lookup"><span data-stu-id="10ac1-115">'T</span></span>

<span data-ttu-id="10ac1-116">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="10ac1-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="10ac1-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="10ac1-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="10ac1-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="10ac1-118">See Also</span></span>

- [<span data-ttu-id="10ac1-119">Microsoft.Quantum.Arrays.SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="10ac1-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)