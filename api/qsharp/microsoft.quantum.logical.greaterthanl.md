---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: Função GreaterThanL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197981"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="53fff-102">Função GreaterThanL</span><span class="sxs-lookup"><span data-stu-id="53fff-102">GreaterThanL function</span></span>

<span data-ttu-id="53fff-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="53fff-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="53fff-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53fff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53fff-105">Retorna verdadeira se e somente se um número for maior que outro número.</span><span class="sxs-lookup"><span data-stu-id="53fff-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="53fff-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="53fff-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="53fff-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="53fff-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="53fff-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="53fff-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="53fff-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="53fff-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="53fff-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="53fff-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="53fff-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="53fff-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="53fff-112">`true` se e somente se `a` for estritamente maior do que `b` .</span><span class="sxs-lookup"><span data-stu-id="53fff-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="53fff-113">Observações</span><span class="sxs-lookup"><span data-stu-id="53fff-113">Remarks</span></span>

<span data-ttu-id="53fff-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="53fff-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```