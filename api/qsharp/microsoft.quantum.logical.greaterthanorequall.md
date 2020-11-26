---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: Função GreaterThanOrEqual
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197760"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="e2ce4-102">Função GreaterThanOrEqual</span><span class="sxs-lookup"><span data-stu-id="e2ce4-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="e2ce4-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e2ce4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e2ce4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2ce4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2ce4-105">Retorna verdadeira se e somente se um número for maior ou igual a outro número.</span><span class="sxs-lookup"><span data-stu-id="e2ce4-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e2ce4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e2ce4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e2ce4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e2ce4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e2ce4-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="e2ce4-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e2ce4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e2ce4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e2ce4-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="e2ce4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e2ce4-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e2ce4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e2ce4-112">`true` se e somente se `a` for maior do que ou é igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="e2ce4-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2ce4-113">Observações</span><span class="sxs-lookup"><span data-stu-id="e2ce4-113">Remarks</span></span>

<span data-ttu-id="e2ce4-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="e2ce4-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```