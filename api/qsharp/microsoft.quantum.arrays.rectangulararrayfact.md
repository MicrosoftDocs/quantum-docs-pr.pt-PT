---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Função RectangularArrayFact
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718919"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="33178-102">Função RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="33178-102">RectangularArrayFact function</span></span>

<span data-ttu-id="33178-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="33178-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="33178-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33178-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33178-105">Representa uma condição de que uma matriz bidimensional tem uma forma retangular</span><span class="sxs-lookup"><span data-stu-id="33178-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="33178-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="33178-106">Description</span></span>

<span data-ttu-id="33178-107">Esta função afirma que cada linha de uma matriz tem o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="33178-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="33178-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="33178-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="33178-109">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="33178-109">array : 'T[][]</span></span>

<span data-ttu-id="33178-110">Uma matriz bidimensional de elementos</span><span class="sxs-lookup"><span data-stu-id="33178-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="33178-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="33178-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="33178-112">Uma mensagem a ser impressa se a matriz não for uma matriz retangular</span><span class="sxs-lookup"><span data-stu-id="33178-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="33178-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33178-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33178-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="33178-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33178-115">'T</span><span class="sxs-lookup"><span data-stu-id="33178-115">'T</span></span>

<span data-ttu-id="33178-116">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="33178-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="33178-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="33178-117">See Also</span></span>

- [<span data-ttu-id="33178-118">Microsoft.Quantum.Arrays.SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="33178-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)