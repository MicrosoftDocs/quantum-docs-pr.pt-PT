---
uid: Microsoft.Quantum.Logical.EqualB
title: Função EqualB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: b566f5ba8548eadeecf63a1e91956d936e7e9a20
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198474"
---
# <a name="equalb-function"></a><span data-ttu-id="cd6ff-102">Função EqualB</span><span class="sxs-lookup"><span data-stu-id="cd6ff-102">EqualB function</span></span>

<span data-ttu-id="cd6ff-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cd6ff-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cd6ff-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd6ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd6ff-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="cd6ff-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="cd6ff-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cd6ff-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="cd6ff-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd6ff-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd6ff-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="cd6ff-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="cd6ff-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd6ff-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd6ff-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="cd6ff-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cd6ff-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd6ff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd6ff-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="cd6ff-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd6ff-113">Observações</span><span class="sxs-lookup"><span data-stu-id="cd6ff-113">Remarks</span></span>

<span data-ttu-id="cd6ff-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="cd6ff-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```