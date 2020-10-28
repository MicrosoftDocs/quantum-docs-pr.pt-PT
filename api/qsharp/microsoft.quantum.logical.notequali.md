---
uid: Microsoft.Quantum.Logical.NotEqualI
title: Não Função NotEqualI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709827"
---
# <a name="notequali-function"></a><span data-ttu-id="a22b7-102">Não Função NotEqualI</span><span class="sxs-lookup"><span data-stu-id="a22b7-102">NotEqualI function</span></span>

<span data-ttu-id="a22b7-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a22b7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a22b7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a22b7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a22b7-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="a22b7-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="a22b7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a22b7-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a22b7-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a22b7-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a22b7-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a22b7-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="a22b7-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a22b7-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a22b7-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a22b7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a22b7-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a22b7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a22b7-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="a22b7-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a22b7-113">Observações</span><span class="sxs-lookup"><span data-stu-id="a22b7-113">Remarks</span></span>

<span data-ttu-id="a22b7-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a22b7-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```