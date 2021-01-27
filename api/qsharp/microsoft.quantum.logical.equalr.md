---
uid: Microsoft.Quantum.Logical.EqualR
title: Função EqualR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815982"
---
# <a name="equalr-function"></a><span data-ttu-id="2e1a3-102">Função EqualR</span><span class="sxs-lookup"><span data-stu-id="2e1a3-102">EqualR function</span></span>

<span data-ttu-id="2e1a3-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2e1a3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2e1a3-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e1a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e1a3-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="2e1a3-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="2e1a3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e1a3-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="2e1a3-107">a : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e1a3-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="2e1a3-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="2e1a3-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="2e1a3-109">b : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e1a3-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="2e1a3-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="2e1a3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2e1a3-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e1a3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e1a3-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="2e1a3-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e1a3-113">Observações</span><span class="sxs-lookup"><span data-stu-id="2e1a3-113">Remarks</span></span>

<span data-ttu-id="2e1a3-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="2e1a3-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```