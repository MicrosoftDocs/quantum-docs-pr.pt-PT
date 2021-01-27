---
uid: Microsoft.Quantum.Logical.EqualI
title: Função EqualI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816756"
---
# <a name="equali-function"></a><span data-ttu-id="fd0fb-102">Função EqualI</span><span class="sxs-lookup"><span data-stu-id="fd0fb-102">EqualI function</span></span>

<span data-ttu-id="fd0fb-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fd0fb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fd0fb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd0fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd0fb-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="fd0fb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fd0fb-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fd0fb-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd0fb-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd0fb-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="fd0fb-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd0fb-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd0fb-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fd0fb-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fd0fb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd0fb-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="fd0fb-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd0fb-113">Observações</span><span class="sxs-lookup"><span data-stu-id="fd0fb-113">Remarks</span></span>

<span data-ttu-id="fd0fb-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="fd0fb-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```