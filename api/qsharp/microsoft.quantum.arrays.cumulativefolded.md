---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Função CumulativeFolded
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719398"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="0be86-102">Função CumulativeFolded</span><span class="sxs-lookup"><span data-stu-id="0be86-102">CumulativeFolded function</span></span>

<span data-ttu-id="0be86-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0be86-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0be86-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0be86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0be86-105">Combina Mapeado e Dobre numa única função</span><span class="sxs-lookup"><span data-stu-id="0be86-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="0be86-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0be86-106">Description</span></span>

<span data-ttu-id="0be86-107">Esta função iteriza a `fn` função através da matriz, partindo de um estado inicial `state` e devolve todos os valores intermédios, sem incluir o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="0be86-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="0be86-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0be86-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="0be86-109">fn : ('Estado,'T) -> 'Estado</span><span class="sxs-lookup"><span data-stu-id="0be86-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="0be86-110">Uma função a ser dobrada sobre a matriz</span><span class="sxs-lookup"><span data-stu-id="0be86-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="0be86-111">estado : 'Estado</span><span class="sxs-lookup"><span data-stu-id="0be86-111">state : 'State</span></span>

<span data-ttu-id="0be86-112">O estado inicial a ser dobrado</span><span class="sxs-lookup"><span data-stu-id="0be86-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="0be86-113">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="0be86-113">array : 'T[]</span></span>

<span data-ttu-id="0be86-114">Uma matriz de valores a dobrar</span><span class="sxs-lookup"><span data-stu-id="0be86-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="0be86-115">Saída : 'Estado].</span><span class="sxs-lookup"><span data-stu-id="0be86-115">Output : 'State[]</span></span>

<span data-ttu-id="0be86-116">Todos os estados intermédios, incluindo o estado final, mas não o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="0be86-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="0be86-117">O comprimento da matriz de saída tem o mesmo comprimento que `array` . .</span><span class="sxs-lookup"><span data-stu-id="0be86-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0be86-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0be86-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="0be86-119">'Estado</span><span class="sxs-lookup"><span data-stu-id="0be86-119">'State</span></span>

<span data-ttu-id="0be86-120">O tipo de estados em que a `fn` função funciona, ou seja, aceita como primeira entrada e retorno.</span><span class="sxs-lookup"><span data-stu-id="0be86-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="0be86-121">'T</span><span class="sxs-lookup"><span data-stu-id="0be86-121">'T</span></span>

<span data-ttu-id="0be86-122">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="0be86-122">The type of `array` elements.</span></span>