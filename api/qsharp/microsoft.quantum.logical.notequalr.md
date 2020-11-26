---
uid: Microsoft.Quantum.Logical.NotEqualR
title: Função NotEqualR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197199"
---
# <a name="notequalr-function"></a><span data-ttu-id="8dea1-102">Função NotEqualR</span><span class="sxs-lookup"><span data-stu-id="8dea1-102">NotEqualR function</span></span>

<span data-ttu-id="8dea1-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8dea1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8dea1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8dea1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8dea1-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="8dea1-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="8dea1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8dea1-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="8dea1-107">a : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="8dea1-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="8dea1-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="8dea1-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="8dea1-109">b : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="8dea1-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="8dea1-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="8dea1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8dea1-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8dea1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8dea1-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="8dea1-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8dea1-113">Observações</span><span class="sxs-lookup"><span data-stu-id="8dea1-113">Remarks</span></span>

<span data-ttu-id="8dea1-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="8dea1-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```