---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Função desapertado
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219962"
---
# <a name="unzipped-function"></a><span data-ttu-id="d55f0-102">Função desapertado</span><span class="sxs-lookup"><span data-stu-id="d55f0-102">Unzipped function</span></span>

<span data-ttu-id="d55f0-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d55f0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d55f0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d55f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d55f0-105">Dada uma matriz de 2 tuples, devolve um tuple de duas matrizes, cada uma contendo os elementos dos tuples da matriz de entrada.</span><span class="sxs-lookup"><span data-stu-id="d55f0-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="d55f0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d55f0-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="d55f0-107">arr : ('T,'U)[]</span><span class="sxs-lookup"><span data-stu-id="d55f0-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="d55f0-108">Uma matriz contendo 2 tuples</span><span class="sxs-lookup"><span data-stu-id="d55f0-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="d55f0-109">Saída : ('T],'U[])</span><span class="sxs-lookup"><span data-stu-id="d55f0-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="d55f0-110">Duas matrizes, a primeira contendo todos os primeiros elementos dos tuples de entrada, a segunda contendo todos os segundos elementos dos tuples de entrada.</span><span class="sxs-lookup"><span data-stu-id="d55f0-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d55f0-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d55f0-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d55f0-112">'T</span><span class="sxs-lookup"><span data-stu-id="d55f0-112">'T</span></span>

<span data-ttu-id="d55f0-113">O tipo do primeiro elemento em cada tuple</span><span class="sxs-lookup"><span data-stu-id="d55f0-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="d55f0-114">'U</span><span class="sxs-lookup"><span data-stu-id="d55f0-114">'U</span></span>

<span data-ttu-id="d55f0-115">O tipo do segundo elemento em cada tuple</span><span class="sxs-lookup"><span data-stu-id="d55f0-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="d55f0-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d55f0-116">See Also</span></span>

- [<span data-ttu-id="d55f0-117">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="d55f0-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)