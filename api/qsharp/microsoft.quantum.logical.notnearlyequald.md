---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: Não SenlyEqualD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720730"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="a6008-102">Não SenlyEqualD</span><span class="sxs-lookup"><span data-stu-id="a6008-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="a6008-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a6008-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a6008-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6008-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6008-105">Retornas verdadeiras se e somente se duas entradas não forem quase iguais (isto é, não estão dentro de uma tolerância de 1e-12).</span><span class="sxs-lookup"><span data-stu-id="a6008-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="a6008-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a6008-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="a6008-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a6008-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a6008-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a6008-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="a6008-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a6008-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a6008-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="a6008-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a6008-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a6008-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a6008-112">`true` se e somente se `a` não for quase igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="a6008-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6008-113">Observações</span><span class="sxs-lookup"><span data-stu-id="a6008-113">Remarks</span></span>

<span data-ttu-id="a6008-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a6008-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```