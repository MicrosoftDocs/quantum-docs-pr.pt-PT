---
uid: Microsoft.Quantum.Logical.NotEqualD
title: Função NotEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723478"
---
# <a name="notequald-function"></a><span data-ttu-id="ab70b-102">Função NotEqualD</span><span class="sxs-lookup"><span data-stu-id="ab70b-102">NotEqualD function</span></span>

<span data-ttu-id="ab70b-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ab70b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ab70b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab70b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab70b-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="ab70b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ab70b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ab70b-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ab70b-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab70b-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab70b-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ab70b-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ab70b-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ab70b-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ab70b-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ab70b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ab70b-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab70b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab70b-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="ab70b-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab70b-113">Observações</span><span class="sxs-lookup"><span data-stu-id="ab70b-113">Remarks</span></span>

<span data-ttu-id="ab70b-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="ab70b-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```