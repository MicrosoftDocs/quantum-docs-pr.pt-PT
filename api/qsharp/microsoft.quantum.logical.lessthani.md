---
uid: Microsoft.Quantum.Logical.LessThanI
title: Função LessThanI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815825"
---
# <a name="lessthani-function"></a><span data-ttu-id="10c2d-102">Função LessThanI</span><span class="sxs-lookup"><span data-stu-id="10c2d-102">LessThanI function</span></span>

<span data-ttu-id="10c2d-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="10c2d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="10c2d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10c2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10c2d-105">Retorna verdadeira se e somente se um número for inferior a outro número.</span><span class="sxs-lookup"><span data-stu-id="10c2d-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="10c2d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="10c2d-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="10c2d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10c2d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10c2d-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="10c2d-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="10c2d-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10c2d-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="10c2d-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="10c2d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="10c2d-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="10c2d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="10c2d-112">`true` se e somente se `a` for estritamente inferior `b` a .</span><span class="sxs-lookup"><span data-stu-id="10c2d-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="10c2d-113">Observações</span><span class="sxs-lookup"><span data-stu-id="10c2d-113">Remarks</span></span>

<span data-ttu-id="10c2d-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="10c2d-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```