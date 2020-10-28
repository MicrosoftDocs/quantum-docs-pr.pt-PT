---
uid: Microsoft.Quantum.Core.RangeStart
title: Função RangeStart
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713170"
---
# <a name="rangestart-function"></a><span data-ttu-id="5a580-102">Função RangeStart</span><span class="sxs-lookup"><span data-stu-id="5a580-102">RangeStart function</span></span>

<span data-ttu-id="5a580-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="5a580-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="5a580-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a580-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a580-105">Devolve o valor de início definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="5a580-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="5a580-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5a580-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="5a580-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="5a580-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="5a580-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a580-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a580-109">O valor inicial definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="5a580-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a580-110">Observações</span><span class="sxs-lookup"><span data-stu-id="5a580-110">Remarks</span></span>

<span data-ttu-id="5a580-111">O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.</span><span class="sxs-lookup"><span data-stu-id="5a580-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="5a580-112">Note que o valor inicial definido de uma gama é o mesmo que o primeiro elemento da sequência, a menos que o intervalo especifique uma sequência vazia (por exemplo, 2 ..</span><span class="sxs-lookup"><span data-stu-id="5a580-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="5a580-113">1).</span><span class="sxs-lookup"><span data-stu-id="5a580-113">1).</span></span>