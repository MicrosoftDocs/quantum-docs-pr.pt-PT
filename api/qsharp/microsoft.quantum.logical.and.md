---
uid: Microsoft.Quantum.Logical.And
title: E funcionar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849234"
---
# <a name="and-function"></a><span data-ttu-id="edeb5-102">E funcionar</span><span class="sxs-lookup"><span data-stu-id="edeb5-102">And function</span></span>

<span data-ttu-id="edeb5-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="edeb5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="edeb5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="edeb5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="edeb5-105">Devolve a conjunção Booleana de dois valores.</span><span class="sxs-lookup"><span data-stu-id="edeb5-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="edeb5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="edeb5-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="edeb5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="edeb5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="edeb5-108">O primeiro valor a ser considerado.</span><span class="sxs-lookup"><span data-stu-id="edeb5-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="edeb5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="edeb5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="edeb5-110">O segundo valor a considerar.</span><span class="sxs-lookup"><span data-stu-id="edeb5-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="edeb5-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="edeb5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="edeb5-112">`true` se e somente se `a` e `b` são ambos `true` .</span><span class="sxs-lookup"><span data-stu-id="edeb5-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="edeb5-113">Observações</span><span class="sxs-lookup"><span data-stu-id="edeb5-113">Remarks</span></span>

<span data-ttu-id="edeb5-114">Ao contrário do `and` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="edeb5-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="edeb5-115">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="edeb5-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```