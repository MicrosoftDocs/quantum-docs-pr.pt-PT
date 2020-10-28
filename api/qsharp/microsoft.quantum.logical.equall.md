---
uid: Microsoft.Quantum.Logical.EqualL
title: Função EqualL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710037"
---
# <a name="equall-function"></a><span data-ttu-id="a837f-102">Função EqualL</span><span class="sxs-lookup"><span data-stu-id="a837f-102">EqualL function</span></span>

<span data-ttu-id="a837f-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a837f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a837f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a837f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a837f-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="a837f-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="a837f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a837f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="a837f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a837f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a837f-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a837f-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="a837f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a837f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a837f-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a837f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a837f-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a837f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a837f-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="a837f-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a837f-113">Observações</span><span class="sxs-lookup"><span data-stu-id="a837f-113">Remarks</span></span>

<span data-ttu-id="a837f-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a837f-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```