---
uid: Microsoft.Quantum.Logical.Or
title: Ou função
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197131"
---
# <a name="or-function"></a><span data-ttu-id="d1073-102">Ou função</span><span class="sxs-lookup"><span data-stu-id="d1073-102">Or function</span></span>

<span data-ttu-id="d1073-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d1073-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d1073-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1073-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1073-105">Devolve a disjunção booleana de dois valores.</span><span class="sxs-lookup"><span data-stu-id="d1073-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="d1073-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1073-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d1073-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d1073-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d1073-108">O primeiro valor a ser considerado.</span><span class="sxs-lookup"><span data-stu-id="d1073-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="d1073-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d1073-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d1073-110">O segundo valor a considerar.</span><span class="sxs-lookup"><span data-stu-id="d1073-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d1073-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d1073-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d1073-112">`true` se e somente se `a` um ou o são `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="d1073-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1073-113">Observações</span><span class="sxs-lookup"><span data-stu-id="d1073-113">Remarks</span></span>

<span data-ttu-id="d1073-114">Ao contrário do `or` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="d1073-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="d1073-115">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="d1073-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```