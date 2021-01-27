---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: Função LessThanOrEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 703b782efe9daccd4f6a339481d49ae9232123f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849128"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="6dbec-102">Função LessThanOrEqualD</span><span class="sxs-lookup"><span data-stu-id="6dbec-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="6dbec-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6dbec-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6dbec-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6dbec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6dbec-105">Retorna verdadeira se e somente se um número for inferior ou igual a outro número.</span><span class="sxs-lookup"><span data-stu-id="6dbec-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6dbec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6dbec-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6dbec-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6dbec-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6dbec-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="6dbec-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6dbec-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6dbec-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6dbec-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="6dbec-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6dbec-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6dbec-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6dbec-112">`true` se e somente se `a` for inferior ou igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="6dbec-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6dbec-113">Observações</span><span class="sxs-lookup"><span data-stu-id="6dbec-113">Remarks</span></span>

<span data-ttu-id="6dbec-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6dbec-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```