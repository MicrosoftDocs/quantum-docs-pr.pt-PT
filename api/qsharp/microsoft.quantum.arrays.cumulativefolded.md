---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Função CumulativeFolded
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210034"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="d34ad-102">Função CumulativeFolded</span><span class="sxs-lookup"><span data-stu-id="d34ad-102">CumulativeFolded function</span></span>

<span data-ttu-id="d34ad-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d34ad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d34ad-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d34ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d34ad-105">Combina Mapeado e Dobre numa única função</span><span class="sxs-lookup"><span data-stu-id="d34ad-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="d34ad-106">Description</span><span class="sxs-lookup"><span data-stu-id="d34ad-106">Description</span></span>

<span data-ttu-id="d34ad-107">Esta função iteriza a `fn` função através da matriz, partindo de um estado inicial `state` e devolve todos os valores intermédios, sem incluir o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="d34ad-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="d34ad-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d34ad-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="d34ad-109">fn : ('Estado,'T) -> 'Estado</span><span class="sxs-lookup"><span data-stu-id="d34ad-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="d34ad-110">Uma função a ser dobrada sobre a matriz</span><span class="sxs-lookup"><span data-stu-id="d34ad-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="d34ad-111">estado : 'Estado</span><span class="sxs-lookup"><span data-stu-id="d34ad-111">state : 'State</span></span>

<span data-ttu-id="d34ad-112">O estado inicial a ser dobrado</span><span class="sxs-lookup"><span data-stu-id="d34ad-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="d34ad-113">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d34ad-113">array : 'T[]</span></span>

<span data-ttu-id="d34ad-114">Uma matriz de valores a dobrar</span><span class="sxs-lookup"><span data-stu-id="d34ad-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="d34ad-115">Saída : 'Estado].</span><span class="sxs-lookup"><span data-stu-id="d34ad-115">Output : 'State[]</span></span>

<span data-ttu-id="d34ad-116">Todos os estados intermédios, incluindo o estado final, mas não o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="d34ad-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="d34ad-117">O comprimento da matriz de saída tem o mesmo comprimento que `array` . .</span><span class="sxs-lookup"><span data-stu-id="d34ad-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d34ad-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d34ad-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="d34ad-119">'Estado</span><span class="sxs-lookup"><span data-stu-id="d34ad-119">'State</span></span>

<span data-ttu-id="d34ad-120">O tipo de estados em que a `fn` função funciona, ou seja, aceita como primeira entrada e retorno.</span><span class="sxs-lookup"><span data-stu-id="d34ad-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="d34ad-121">'T</span><span class="sxs-lookup"><span data-stu-id="d34ad-121">'T</span></span>

<span data-ttu-id="d34ad-122">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="d34ad-122">The type of `array` elements.</span></span>