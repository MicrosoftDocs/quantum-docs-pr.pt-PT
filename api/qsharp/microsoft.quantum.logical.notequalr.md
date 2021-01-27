---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Função NotEqualR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848506"
---
# <a name="notequalr-function"></a><span data-ttu-id="c2dd7-102">Função NotEqualR</span><span class="sxs-lookup"><span data-stu-id="c2dd7-102">NotEqualR function</span></span>

<span data-ttu-id="c2dd7-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c2dd7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c2dd7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2dd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2dd7-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="c2dd7-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="c2dd7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c2dd7-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="c2dd7-107">a : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="c2dd7-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="c2dd7-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="c2dd7-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="c2dd7-109">b : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="c2dd7-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="c2dd7-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="c2dd7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c2dd7-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c2dd7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c2dd7-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="c2dd7-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2dd7-113">Observações</span><span class="sxs-lookup"><span data-stu-id="c2dd7-113">Remarks</span></span>

<span data-ttu-id="c2dd7-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c2dd7-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```