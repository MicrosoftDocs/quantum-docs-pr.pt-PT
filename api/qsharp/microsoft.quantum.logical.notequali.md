---
uid: Microsoft.Quantum.Logical.NotEqualI
title: Não Função NotEqualI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814513"
---
# <a name="notequali-function"></a><span data-ttu-id="942c8-102">Não Função NotEqualI</span><span class="sxs-lookup"><span data-stu-id="942c8-102">NotEqualI function</span></span>

<span data-ttu-id="942c8-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="942c8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="942c8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="942c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="942c8-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="942c8-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="942c8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="942c8-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="942c8-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="942c8-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="942c8-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="942c8-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="942c8-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="942c8-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="942c8-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="942c8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="942c8-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="942c8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="942c8-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="942c8-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="942c8-113">Observações</span><span class="sxs-lookup"><span data-stu-id="942c8-113">Remarks</span></span>

<span data-ttu-id="942c8-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="942c8-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```