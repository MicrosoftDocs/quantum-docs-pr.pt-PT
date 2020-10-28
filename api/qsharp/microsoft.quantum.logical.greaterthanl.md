---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: Função GreaterThanL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711381"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="b5589-102">Função GreaterThanL</span><span class="sxs-lookup"><span data-stu-id="b5589-102">GreaterThanL function</span></span>

<span data-ttu-id="b5589-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b5589-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b5589-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5589-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5589-105">Retorna verdadeira se e somente se um número for maior que outro número.</span><span class="sxs-lookup"><span data-stu-id="b5589-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b5589-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b5589-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b5589-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b5589-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b5589-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="b5589-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b5589-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b5589-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b5589-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="b5589-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b5589-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5589-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5589-112">`true` se e somente se `a` for estritamente maior do que `b` .</span><span class="sxs-lookup"><span data-stu-id="b5589-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5589-113">Observações</span><span class="sxs-lookup"><span data-stu-id="b5589-113">Remarks</span></span>

<span data-ttu-id="b5589-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="b5589-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```