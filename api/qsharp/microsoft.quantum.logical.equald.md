---
uid: Microsoft.Quantum.Logical.EqualD
title: Função EqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711395"
---
# <a name="equald-function"></a><span data-ttu-id="1d32d-102">Função EqualD</span><span class="sxs-lookup"><span data-stu-id="1d32d-102">EqualD function</span></span>

<span data-ttu-id="1d32d-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1d32d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1d32d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d32d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d32d-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="1d32d-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="1d32d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1d32d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="1d32d-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1d32d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1d32d-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1d32d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="1d32d-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1d32d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1d32d-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1d32d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1d32d-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1d32d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1d32d-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="1d32d-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d32d-113">Observações</span><span class="sxs-lookup"><span data-stu-id="1d32d-113">Remarks</span></span>

<span data-ttu-id="1d32d-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="1d32d-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```