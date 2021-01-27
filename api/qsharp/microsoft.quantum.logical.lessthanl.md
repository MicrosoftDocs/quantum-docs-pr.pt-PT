---
uid: Microsoft.Quantum.Logical.LessThanL
title: Função LessThanL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849155"
---
# <a name="lessthanl-function"></a><span data-ttu-id="ea5cc-102">Função LessThanL</span><span class="sxs-lookup"><span data-stu-id="ea5cc-102">LessThanL function</span></span>

<span data-ttu-id="ea5cc-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ea5cc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ea5cc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea5cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea5cc-105">Retorna verdadeira se e somente se um número for inferior a outro número.</span><span class="sxs-lookup"><span data-stu-id="ea5cc-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="ea5cc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ea5cc-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ea5cc-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ea5cc-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ea5cc-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ea5cc-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="ea5cc-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ea5cc-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ea5cc-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ea5cc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ea5cc-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ea5cc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ea5cc-112">`true` se e somente se `a` for estritamente inferior `b` a .</span><span class="sxs-lookup"><span data-stu-id="ea5cc-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea5cc-113">Observações</span><span class="sxs-lookup"><span data-stu-id="ea5cc-113">Remarks</span></span>

<span data-ttu-id="ea5cc-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="ea5cc-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```