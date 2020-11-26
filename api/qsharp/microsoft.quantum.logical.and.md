---
uid: Microsoft.Quantum.Logical.And
title: E funcionar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198576"
---
# <a name="and-function"></a><span data-ttu-id="3ca40-102">E funcionar</span><span class="sxs-lookup"><span data-stu-id="3ca40-102">And function</span></span>

<span data-ttu-id="3ca40-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3ca40-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3ca40-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ca40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ca40-105">Devolve a conjunção Booleana de dois valores.</span><span class="sxs-lookup"><span data-stu-id="3ca40-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="3ca40-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ca40-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="3ca40-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3ca40-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3ca40-108">O primeiro valor a ser considerado.</span><span class="sxs-lookup"><span data-stu-id="3ca40-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="3ca40-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3ca40-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3ca40-110">O segundo valor a considerar.</span><span class="sxs-lookup"><span data-stu-id="3ca40-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3ca40-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3ca40-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3ca40-112">`true` se e somente se `a` e `b` são ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="3ca40-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ca40-113">Observações</span><span class="sxs-lookup"><span data-stu-id="3ca40-113">Remarks</span></span>

<span data-ttu-id="3ca40-114">Ao contrário do `and` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="3ca40-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="3ca40-115">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3ca40-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```