---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: Função GreaterThanOrEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 9d794fa94c1ccbde4030c90198fd7c7654469876
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711378"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="11dfa-102">Função GreaterThanOrEqualD</span><span class="sxs-lookup"><span data-stu-id="11dfa-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="11dfa-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="11dfa-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="11dfa-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11dfa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11dfa-105">Retorna verdadeira se e somente se um número for maior ou igual a outro número.</span><span class="sxs-lookup"><span data-stu-id="11dfa-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="11dfa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="11dfa-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="11dfa-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="11dfa-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="11dfa-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="11dfa-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="11dfa-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="11dfa-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="11dfa-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="11dfa-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="11dfa-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="11dfa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="11dfa-112">`true` se e somente se `a` for maior do que ou é igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="11dfa-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="11dfa-113">Observações</span><span class="sxs-lookup"><span data-stu-id="11dfa-113">Remarks</span></span>

<span data-ttu-id="11dfa-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="11dfa-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```