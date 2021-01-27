---
uid: Microsoft.Quantum.Arrays.Fold
title: Função dobrável
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848611"
---
# <a name="fold-function"></a><span data-ttu-id="53aa9-102">Função dobrável</span><span class="sxs-lookup"><span data-stu-id="53aa9-102">Fold function</span></span>

<span data-ttu-id="53aa9-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="53aa9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="53aa9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53aa9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53aa9-105">Iterates uma função `f` através de uma `array` matriz, retornando `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="53aa9-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="53aa9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="53aa9-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="53aa9-107">pasta : ('Estado,'T) -> 'Estado</span><span class="sxs-lookup"><span data-stu-id="53aa9-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="53aa9-108">Uma função a ser dobrada sobre a matriz.</span><span class="sxs-lookup"><span data-stu-id="53aa9-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="53aa9-109">estado : 'Estado</span><span class="sxs-lookup"><span data-stu-id="53aa9-109">state : 'State</span></span>

<span data-ttu-id="53aa9-110">O estado inicial da pasta.</span><span class="sxs-lookup"><span data-stu-id="53aa9-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="53aa9-111">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="53aa9-111">array : 'T[]</span></span>

<span data-ttu-id="53aa9-112">Uma variedade de valores a dobrar.</span><span class="sxs-lookup"><span data-stu-id="53aa9-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="53aa9-113">Saída : 'Estado</span><span class="sxs-lookup"><span data-stu-id="53aa9-113">Output : 'State</span></span>

<span data-ttu-id="53aa9-114">O estado final devolvido pela pasta depois de iterar sobre todos os elementos de `array` .</span><span class="sxs-lookup"><span data-stu-id="53aa9-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="53aa9-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="53aa9-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="53aa9-116">'Estado</span><span class="sxs-lookup"><span data-stu-id="53aa9-116">'State</span></span>

<span data-ttu-id="53aa9-117">O tipo de estados em que a `folder` função funciona, ou seja, aceita como primeiro argumento e regressa.</span><span class="sxs-lookup"><span data-stu-id="53aa9-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="53aa9-118">'T</span><span class="sxs-lookup"><span data-stu-id="53aa9-118">'T</span></span>

<span data-ttu-id="53aa9-119">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="53aa9-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="53aa9-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="53aa9-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```