---
uid: Microsoft.Quantum.Logical.LessThanL
title: Função LessThanL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197726"
---
# <a name="lessthanl-function"></a><span data-ttu-id="281eb-102">Função LessThanL</span><span class="sxs-lookup"><span data-stu-id="281eb-102">LessThanL function</span></span>

<span data-ttu-id="281eb-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="281eb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="281eb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="281eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="281eb-105">Retorna verdadeira se e somente se um número for inferior a outro número.</span><span class="sxs-lookup"><span data-stu-id="281eb-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="281eb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="281eb-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="281eb-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="281eb-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="281eb-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="281eb-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="281eb-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="281eb-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="281eb-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="281eb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="281eb-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="281eb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="281eb-112">`true` se e somente se `a` for estritamente inferior `b` a .</span><span class="sxs-lookup"><span data-stu-id="281eb-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="281eb-113">Observações</span><span class="sxs-lookup"><span data-stu-id="281eb-113">Remarks</span></span>

<span data-ttu-id="281eb-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="281eb-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```