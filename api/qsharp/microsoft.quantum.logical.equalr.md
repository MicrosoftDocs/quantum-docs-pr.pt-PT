---
uid: Microsoft.Quantum.Logical.EqualR
title: Função EqualR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710034"
---
# <a name="equalr-function"></a><span data-ttu-id="2e701-102">Função EqualR</span><span class="sxs-lookup"><span data-stu-id="2e701-102">EqualR function</span></span>

<span data-ttu-id="2e701-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2e701-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2e701-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e701-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e701-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="2e701-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="2e701-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e701-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="2e701-107">a : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e701-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="2e701-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="2e701-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="2e701-109">b : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e701-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="2e701-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="2e701-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2e701-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e701-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e701-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="2e701-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e701-113">Observações</span><span class="sxs-lookup"><span data-stu-id="2e701-113">Remarks</span></span>

<span data-ttu-id="2e701-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="2e701-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```