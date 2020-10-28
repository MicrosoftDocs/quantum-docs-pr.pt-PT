---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: Função GreaterThanOrEqualI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723495"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="ddbbc-102">Função GreaterThanOrEqualI</span><span class="sxs-lookup"><span data-stu-id="ddbbc-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="ddbbc-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ddbbc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ddbbc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddbbc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddbbc-105">Retorna verdadeira se e somente se um número for maior ou igual a outro número.</span><span class="sxs-lookup"><span data-stu-id="ddbbc-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="ddbbc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ddbbc-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ddbbc-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddbbc-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddbbc-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ddbbc-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="ddbbc-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddbbc-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddbbc-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ddbbc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ddbbc-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ddbbc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ddbbc-112">`true` se e somente se `a` for maior do que ou é igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="ddbbc-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ddbbc-113">Observações</span><span class="sxs-lookup"><span data-stu-id="ddbbc-113">Remarks</span></span>

<span data-ttu-id="ddbbc-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="ddbbc-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```