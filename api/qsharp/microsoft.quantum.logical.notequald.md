---
uid: Microsoft.Quantum.Logical.NotEqualD
title: Função NotEqualD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4599d7125dbc67547af454183f620e8d84f2caf7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197250"
---
# <a name="notequald-function"></a><span data-ttu-id="a723e-102">Função NotEqualD</span><span class="sxs-lookup"><span data-stu-id="a723e-102">NotEqualD function</span></span>

<span data-ttu-id="a723e-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a723e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a723e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a723e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a723e-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="a723e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="a723e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a723e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="a723e-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a723e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a723e-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a723e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="a723e-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a723e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a723e-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a723e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a723e-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a723e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a723e-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="a723e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a723e-113">Observações</span><span class="sxs-lookup"><span data-stu-id="a723e-113">Remarks</span></span>

<span data-ttu-id="a723e-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a723e-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```