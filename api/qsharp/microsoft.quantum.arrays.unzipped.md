---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Função desapertado
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845370"
---
# <a name="unzipped-function"></a><span data-ttu-id="b408d-102">Função desapertado</span><span class="sxs-lookup"><span data-stu-id="b408d-102">Unzipped function</span></span>

<span data-ttu-id="b408d-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b408d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b408d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b408d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b408d-105">Dada uma matriz de 2 tuples, devolve um tuple de duas matrizes, cada uma contendo os elementos dos tuples da matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="b408d-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="b408d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b408d-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="b408d-107">arr : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="b408d-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="b408d-108">Uma matriz contendo 2 tuples</span><span class="sxs-lookup"><span data-stu-id="b408d-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="b408d-109">Saída : ('T],'U[])</span><span class="sxs-lookup"><span data-stu-id="b408d-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="b408d-110">Duas matrizes, a primeira contendo todos os primeiros elementos dos tuples de entrada, a segunda contendo todos os segundos elementos dos tuples de entrada.</span><span class="sxs-lookup"><span data-stu-id="b408d-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b408d-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b408d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b408d-112">'T</span><span class="sxs-lookup"><span data-stu-id="b408d-112">'T</span></span>

<span data-ttu-id="b408d-113">O tipo do primeiro elemento em cada tuple</span><span class="sxs-lookup"><span data-stu-id="b408d-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="b408d-114">'U</span><span class="sxs-lookup"><span data-stu-id="b408d-114">'U</span></span>

<span data-ttu-id="b408d-115">O tipo do segundo elemento em cada tuple</span><span class="sxs-lookup"><span data-stu-id="b408d-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="b408d-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b408d-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="b408d-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b408d-117">See Also</span></span>

- [<span data-ttu-id="b408d-118">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="b408d-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)