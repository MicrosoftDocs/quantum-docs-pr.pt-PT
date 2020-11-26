---
uid: Microsoft.Quantum.Logical.LessThanI
title: Função LessThanI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197777"
---
# <a name="lessthani-function"></a><span data-ttu-id="9ec05-102">Função LessThanI</span><span class="sxs-lookup"><span data-stu-id="9ec05-102">LessThanI function</span></span>

<span data-ttu-id="9ec05-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9ec05-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9ec05-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ec05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ec05-105">Retorna verdadeira se e somente se um número for inferior a outro número.</span><span class="sxs-lookup"><span data-stu-id="9ec05-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="9ec05-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9ec05-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9ec05-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ec05-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ec05-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="9ec05-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="9ec05-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ec05-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9ec05-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="9ec05-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9ec05-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9ec05-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9ec05-112">`true` se e somente se `a` for estritamente inferior `b` a .</span><span class="sxs-lookup"><span data-stu-id="9ec05-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ec05-113">Observações</span><span class="sxs-lookup"><span data-stu-id="9ec05-113">Remarks</span></span>

<span data-ttu-id="9ec05-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="9ec05-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```