---
uid: Microsoft.Quantum.Logical.EqualR
title: Função EqualR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198011"
---
# <a name="equalr-function"></a><span data-ttu-id="017fd-102">Função EqualR</span><span class="sxs-lookup"><span data-stu-id="017fd-102">EqualR function</span></span>

<span data-ttu-id="017fd-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="017fd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="017fd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="017fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="017fd-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="017fd-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="017fd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="017fd-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="017fd-107">a : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="017fd-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="017fd-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="017fd-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="017fd-109">b : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="017fd-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="017fd-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="017fd-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="017fd-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="017fd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="017fd-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="017fd-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="017fd-113">Observações</span><span class="sxs-lookup"><span data-stu-id="017fd-113">Remarks</span></span>

<span data-ttu-id="017fd-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="017fd-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```