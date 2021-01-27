---
uid: Microsoft.Quantum.Core.RangeStep
title: Função RangeStep
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853603"
---
# <a name="rangestep-function"></a><span data-ttu-id="033fa-102">Função RangeStep</span><span class="sxs-lookup"><span data-stu-id="033fa-102">RangeStep function</span></span>

<span data-ttu-id="033fa-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="033fa-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="033fa-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="033fa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="033fa-105">Devolve o inteiro que especifica como o próximo valor de uma gama é calculado.</span><span class="sxs-lookup"><span data-stu-id="033fa-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="033fa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="033fa-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="033fa-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="033fa-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="033fa-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="033fa-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="033fa-109">O valor de passo definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="033fa-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="033fa-110">Observações</span><span class="sxs-lookup"><span data-stu-id="033fa-110">Remarks</span></span>

<span data-ttu-id="033fa-111">O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.</span><span class="sxs-lookup"><span data-stu-id="033fa-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>