---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: Função GreaterThanL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 2247c1c1ae8b37b59e87c0c68b06fd1094c9003b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849207"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="1b2d0-102">Função GreaterThanL</span><span class="sxs-lookup"><span data-stu-id="1b2d0-102">GreaterThanL function</span></span>

<span data-ttu-id="1b2d0-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1b2d0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1b2d0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b2d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b2d0-105">Retorna verdadeira se e somente se um número for maior que outro número.</span><span class="sxs-lookup"><span data-stu-id="1b2d0-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="1b2d0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b2d0-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1b2d0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b2d0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b2d0-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1b2d0-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="1b2d0-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b2d0-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b2d0-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1b2d0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1b2d0-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1b2d0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1b2d0-112">`true` se e somente se `a` for estritamente maior do que `b` .</span><span class="sxs-lookup"><span data-stu-id="1b2d0-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b2d0-113">Observações</span><span class="sxs-lookup"><span data-stu-id="1b2d0-113">Remarks</span></span>

<span data-ttu-id="1b2d0-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="1b2d0-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanL(a, b);
```