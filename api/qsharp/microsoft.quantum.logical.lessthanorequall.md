---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Função LessOrEqual
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197606"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="f9826-102">Função LessOrEqual</span><span class="sxs-lookup"><span data-stu-id="f9826-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="f9826-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f9826-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f9826-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9826-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9826-105">Retorna verdadeira se e somente se um número for inferior ou igual a outro número.</span><span class="sxs-lookup"><span data-stu-id="f9826-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="f9826-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9826-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f9826-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f9826-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f9826-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="f9826-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="f9826-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f9826-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f9826-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="f9826-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f9826-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f9826-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f9826-112">`true` se e somente se `a` for inferior ou igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="f9826-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9826-113">Observações</span><span class="sxs-lookup"><span data-stu-id="f9826-113">Remarks</span></span>

<span data-ttu-id="f9826-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f9826-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```