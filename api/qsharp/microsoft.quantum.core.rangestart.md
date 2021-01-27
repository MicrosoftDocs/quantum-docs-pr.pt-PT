---
uid: Microsoft.Quantum.Core.RangeStart
title: Função RangeStart
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831107"
---
# <a name="rangestart-function"></a><span data-ttu-id="6329d-102">Função RangeStart</span><span class="sxs-lookup"><span data-stu-id="6329d-102">RangeStart function</span></span>

<span data-ttu-id="6329d-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="6329d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="6329d-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6329d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6329d-105">Devolve o valor de início definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="6329d-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="6329d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6329d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="6329d-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="6329d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="6329d-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6329d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6329d-109">O valor inicial definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="6329d-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="6329d-110">Observações</span><span class="sxs-lookup"><span data-stu-id="6329d-110">Remarks</span></span>

<span data-ttu-id="6329d-111">O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.</span><span class="sxs-lookup"><span data-stu-id="6329d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="6329d-112">Note que o valor inicial definido de uma gama é o mesmo que o primeiro elemento da sequência, a menos que o intervalo especifique uma sequência vazia (por exemplo, 2 ..</span><span class="sxs-lookup"><span data-stu-id="6329d-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="6329d-113">1).</span><span class="sxs-lookup"><span data-stu-id="6329d-113">1).</span></span>