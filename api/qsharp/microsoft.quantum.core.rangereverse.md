---
uid: Microsoft.Quantum.Core.RangeReverse
title: Função RangeReverse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213842"
---
# <a name="rangereverse-function"></a><span data-ttu-id="19555-102">Função RangeReverse</span><span class="sxs-lookup"><span data-stu-id="19555-102">RangeReverse function</span></span>

<span data-ttu-id="19555-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="19555-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="19555-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="19555-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="19555-105">Devolve uma nova gama que é o inverso da gama de entrada.</span><span class="sxs-lookup"><span data-stu-id="19555-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="19555-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="19555-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="19555-107">r : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="19555-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="19555-108">Intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="19555-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="19555-109">Saída : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="19555-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="19555-110">Uma nova gama que é o inverso da gama dada.</span><span class="sxs-lookup"><span data-stu-id="19555-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="19555-111">Observações</span><span class="sxs-lookup"><span data-stu-id="19555-111">Remarks</span></span>

<span data-ttu-id="19555-112">Note que o inverso de uma gama não é simplesmente `end` `-step` ... . , porque o último elemento real de uma gama pode não ser o mesmo que . . . . . `start` . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . `end`</span><span class="sxs-lookup"><span data-stu-id="19555-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>