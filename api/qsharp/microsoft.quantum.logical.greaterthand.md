---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: Função GreaterThanD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710006"
---
# <a name="greaterthand-function"></a><span data-ttu-id="036f8-102">Função GreaterThanD</span><span class="sxs-lookup"><span data-stu-id="036f8-102">GreaterThanD function</span></span>

<span data-ttu-id="036f8-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="036f8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="036f8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="036f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="036f8-105">Retorna verdadeira se e somente se um número for maior que outro número.</span><span class="sxs-lookup"><span data-stu-id="036f8-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="036f8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="036f8-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="036f8-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="036f8-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="036f8-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="036f8-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="036f8-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="036f8-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="036f8-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="036f8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="036f8-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="036f8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="036f8-112">`true` se e somente se `a` for estritamente maior do que `b` .</span><span class="sxs-lookup"><span data-stu-id="036f8-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="036f8-113">Observações</span><span class="sxs-lookup"><span data-stu-id="036f8-113">Remarks</span></span>

<span data-ttu-id="036f8-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="036f8-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```