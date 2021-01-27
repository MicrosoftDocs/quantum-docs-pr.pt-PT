---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: Não SenlyEqualD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848492"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="c4a20-102">Não SenlyEqualD</span><span class="sxs-lookup"><span data-stu-id="c4a20-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="c4a20-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c4a20-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c4a20-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4a20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4a20-105">Retornas verdadeiras se e somente se duas entradas não forem quase iguais (isto é, não estão dentro de uma tolerância de 1e-12).</span><span class="sxs-lookup"><span data-stu-id="c4a20-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c4a20-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4a20-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c4a20-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4a20-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4a20-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="c4a20-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c4a20-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4a20-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4a20-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="c4a20-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c4a20-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c4a20-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c4a20-112">`true` se e somente se `a` não for quase igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="c4a20-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4a20-113">Observações</span><span class="sxs-lookup"><span data-stu-id="c4a20-113">Remarks</span></span>

<span data-ttu-id="c4a20-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c4a20-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```