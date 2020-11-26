---
uid: Microsoft.Quantum.Logical.EqualL
title: Função EqualL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198117"
---
# <a name="equall-function"></a><span data-ttu-id="6f46c-102">Função EqualL</span><span class="sxs-lookup"><span data-stu-id="6f46c-102">EqualL function</span></span>

<span data-ttu-id="6f46c-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6f46c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6f46c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f46c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f46c-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="6f46c-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="6f46c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6f46c-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6f46c-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6f46c-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6f46c-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="6f46c-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="6f46c-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6f46c-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6f46c-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="6f46c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6f46c-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6f46c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6f46c-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="6f46c-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f46c-113">Observações</span><span class="sxs-lookup"><span data-stu-id="6f46c-113">Remarks</span></span>

<span data-ttu-id="6f46c-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6f46c-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```