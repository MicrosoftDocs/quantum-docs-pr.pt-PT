---
uid: Microsoft.Quantum.Logical.Or
title: Ou função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719975"
---
# <a name="or-function"></a><span data-ttu-id="96f94-102">Ou função</span><span class="sxs-lookup"><span data-stu-id="96f94-102">Or function</span></span>

<span data-ttu-id="96f94-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="96f94-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="96f94-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96f94-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96f94-105">Devolve a disjunção booleana de dois valores.</span><span class="sxs-lookup"><span data-stu-id="96f94-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="96f94-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96f94-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="96f94-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="96f94-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="96f94-108">O primeiro valor a ser considerado.</span><span class="sxs-lookup"><span data-stu-id="96f94-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="96f94-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="96f94-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="96f94-110">O segundo valor a considerar.</span><span class="sxs-lookup"><span data-stu-id="96f94-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="96f94-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="96f94-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="96f94-112">`true` se e somente se `a` um ou o são `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="96f94-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="96f94-113">Observações</span><span class="sxs-lookup"><span data-stu-id="96f94-113">Remarks</span></span>

<span data-ttu-id="96f94-114">Ao contrário do `or` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="96f94-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="96f94-115">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="96f94-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```