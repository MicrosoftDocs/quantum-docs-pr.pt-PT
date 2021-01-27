---
uid: Microsoft.Quantum.Logical.LessThanD
title: Função LessThanD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849164"
---
# <a name="lessthand-function"></a><span data-ttu-id="91e7b-102">Função LessThanD</span><span class="sxs-lookup"><span data-stu-id="91e7b-102">LessThanD function</span></span>

<span data-ttu-id="91e7b-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="91e7b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="91e7b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91e7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91e7b-105">Retorna verdadeira se e somente se um número for inferior a outro número.</span><span class="sxs-lookup"><span data-stu-id="91e7b-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="91e7b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="91e7b-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="91e7b-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="91e7b-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="91e7b-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="91e7b-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="91e7b-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="91e7b-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="91e7b-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="91e7b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="91e7b-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="91e7b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="91e7b-112">`true` se e somente se `a` for estritamente inferior `b` a .</span><span class="sxs-lookup"><span data-stu-id="91e7b-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="91e7b-113">Observações</span><span class="sxs-lookup"><span data-stu-id="91e7b-113">Remarks</span></span>

<span data-ttu-id="91e7b-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="91e7b-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```