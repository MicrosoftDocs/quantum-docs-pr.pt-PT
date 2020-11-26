---
uid: Microsoft.Quantum.Logical.NotEqualL
title: Função NotEqualL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197233"
---
# <a name="notequall-function"></a><span data-ttu-id="26359-102">Função NotEqualL</span><span class="sxs-lookup"><span data-stu-id="26359-102">NotEqualL function</span></span>

<span data-ttu-id="26359-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="26359-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="26359-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26359-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26359-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="26359-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="26359-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="26359-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="26359-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="26359-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="26359-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="26359-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="26359-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="26359-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="26359-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="26359-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="26359-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26359-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26359-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="26359-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26359-113">Observações</span><span class="sxs-lookup"><span data-stu-id="26359-113">Remarks</span></span>

<span data-ttu-id="26359-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="26359-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```