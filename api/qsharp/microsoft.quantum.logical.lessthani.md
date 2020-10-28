---
uid: Microsoft.Quantum.Logical.LessThanI
title: Função LessThanI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 204e62a87d2b3d0070946985030d038ead686457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723481"
---
# <a name="lessthani-function"></a><span data-ttu-id="1b153-102">Função LessThanI</span><span class="sxs-lookup"><span data-stu-id="1b153-102">LessThanI function</span></span>

<span data-ttu-id="1b153-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1b153-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1b153-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b153-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b153-105">Retorna verdadeira se e somente se um número for inferior a outro número.</span><span class="sxs-lookup"><span data-stu-id="1b153-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="1b153-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b153-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="1b153-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b153-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b153-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1b153-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="1b153-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b153-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b153-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1b153-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1b153-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1b153-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1b153-112">`true` se e somente se `a` for estritamente inferior `b` a .</span><span class="sxs-lookup"><span data-stu-id="1b153-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b153-113">Observações</span><span class="sxs-lookup"><span data-stu-id="1b153-113">Remarks</span></span>

<span data-ttu-id="1b153-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="1b153-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```