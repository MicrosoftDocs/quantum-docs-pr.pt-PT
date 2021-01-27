---
uid: Microsoft.Quantum.Logical.EqualD
title: Função EqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816871"
---
# <a name="equald-function"></a><span data-ttu-id="3df55-102">Função EqualD</span><span class="sxs-lookup"><span data-stu-id="3df55-102">EqualD function</span></span>

<span data-ttu-id="3df55-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3df55-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3df55-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3df55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3df55-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="3df55-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="3df55-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3df55-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="3df55-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3df55-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3df55-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="3df55-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="3df55-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3df55-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3df55-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="3df55-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3df55-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3df55-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3df55-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="3df55-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3df55-113">Observações</span><span class="sxs-lookup"><span data-stu-id="3df55-113">Remarks</span></span>

<span data-ttu-id="3df55-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3df55-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```