---
uid: Microsoft.Quantum.Logical.NotEqualB
title: Função NotEqualB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709838"
---
# <a name="notequalb-function"></a><span data-ttu-id="bf941-102">Função NotEqualB</span><span class="sxs-lookup"><span data-stu-id="bf941-102">NotEqualB function</span></span>

<span data-ttu-id="bf941-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bf941-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bf941-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf941-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf941-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="bf941-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="bf941-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bf941-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="bf941-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf941-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf941-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="bf941-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="bf941-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf941-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf941-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="bf941-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bf941-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bf941-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bf941-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="bf941-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf941-113">Observações</span><span class="sxs-lookup"><span data-stu-id="bf941-113">Remarks</span></span>

<span data-ttu-id="bf941-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="bf941-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```