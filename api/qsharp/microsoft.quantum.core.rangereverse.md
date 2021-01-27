---
uid: Microsoft.Quantum.Core.RangeReverse
title: Função RangeReverse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853647"
---
# <a name="rangereverse-function"></a><span data-ttu-id="e5054-102">Função RangeReverse</span><span class="sxs-lookup"><span data-stu-id="e5054-102">RangeReverse function</span></span>

<span data-ttu-id="e5054-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e5054-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e5054-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e5054-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e5054-105">Devolve uma nova gama que é o inverso da gama de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5054-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="e5054-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e5054-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="e5054-107">r : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e5054-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e5054-108">Intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5054-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="e5054-109">Saída : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e5054-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e5054-110">Uma nova gama que é o inverso da gama dada.</span><span class="sxs-lookup"><span data-stu-id="e5054-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5054-111">Observações</span><span class="sxs-lookup"><span data-stu-id="e5054-111">Remarks</span></span>

<span data-ttu-id="e5054-112">Note que o inverso de uma gama não é simplesmente `end` `-step` `start` ... . , porque o último elemento real de uma gama pode não ser o mesmo que `end` .</span><span class="sxs-lookup"><span data-stu-id="e5054-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>