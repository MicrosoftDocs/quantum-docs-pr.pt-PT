---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Função LessOrEqual
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849119"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="fee83-102">Função LessOrEqual</span><span class="sxs-lookup"><span data-stu-id="fee83-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="fee83-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fee83-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fee83-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fee83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fee83-105">Retorna verdadeira se e somente se um número for inferior ou igual a outro número.</span><span class="sxs-lookup"><span data-stu-id="fee83-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="fee83-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fee83-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="fee83-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fee83-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fee83-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="fee83-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="fee83-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fee83-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fee83-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="fee83-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fee83-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fee83-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fee83-112">`true` se e somente se `a` for inferior ou igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="fee83-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fee83-113">Observações</span><span class="sxs-lookup"><span data-stu-id="fee83-113">Remarks</span></span>

<span data-ttu-id="fee83-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="fee83-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```