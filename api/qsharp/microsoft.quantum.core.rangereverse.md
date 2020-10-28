---
uid: Microsoft.Quantum.Core.RangeReverse
title: Função RangeReverse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713229"
---
# <a name="rangereverse-function"></a><span data-ttu-id="8bd25-102">Função RangeReverse</span><span class="sxs-lookup"><span data-stu-id="8bd25-102">RangeReverse function</span></span>

<span data-ttu-id="8bd25-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="8bd25-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="8bd25-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8bd25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8bd25-105">Devolve uma nova gama que é o inverso da gama de entrada.</span><span class="sxs-lookup"><span data-stu-id="8bd25-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="8bd25-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8bd25-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="8bd25-107">r : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8bd25-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8bd25-108">Intervalo de entrada.</span><span class="sxs-lookup"><span data-stu-id="8bd25-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="8bd25-109">Saída : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8bd25-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="8bd25-110">Uma nova gama que é o inverso da gama dada.</span><span class="sxs-lookup"><span data-stu-id="8bd25-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bd25-111">Observações</span><span class="sxs-lookup"><span data-stu-id="8bd25-111">Remarks</span></span>

<span data-ttu-id="8bd25-112">Note que o inverso de uma gama não é simplesmente `end` `-step` ... . , porque o último elemento real de uma gama pode não ser o mesmo que . . . . . `start` . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . `end`</span><span class="sxs-lookup"><span data-stu-id="8bd25-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>