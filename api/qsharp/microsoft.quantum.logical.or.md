---
uid: Microsoft.Quantum.Logical.Or
title: Ou função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848470"
---
# <a name="or-function"></a><span data-ttu-id="32c36-102">Ou função</span><span class="sxs-lookup"><span data-stu-id="32c36-102">Or function</span></span>

<span data-ttu-id="32c36-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="32c36-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="32c36-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32c36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32c36-105">Devolve a disjunção booleana de dois valores.</span><span class="sxs-lookup"><span data-stu-id="32c36-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="32c36-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="32c36-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="32c36-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32c36-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32c36-108">O primeiro valor a ser considerado.</span><span class="sxs-lookup"><span data-stu-id="32c36-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="32c36-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32c36-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32c36-110">O segundo valor a considerar.</span><span class="sxs-lookup"><span data-stu-id="32c36-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="32c36-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32c36-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32c36-112">`true` se e somente se `a` um ou o são `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="32c36-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="32c36-113">Observações</span><span class="sxs-lookup"><span data-stu-id="32c36-113">Remarks</span></span>

<span data-ttu-id="32c36-114">Ao contrário do `or` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="32c36-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="32c36-115">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="32c36-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```