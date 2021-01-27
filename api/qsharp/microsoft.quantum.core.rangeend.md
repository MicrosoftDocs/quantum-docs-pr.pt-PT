---
uid: Microsoft.Quantum.Core.RangeEnd
title: Função RangeEnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831370"
---
# <a name="rangeend-function"></a><span data-ttu-id="c4782-102">Função RangeEnd</span><span class="sxs-lookup"><span data-stu-id="c4782-102">RangeEnd function</span></span>

<span data-ttu-id="c4782-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="c4782-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="c4782-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c4782-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c4782-105">Devolve o valor final definido da gama dada, que não é necessariamente o último elemento na sequência.</span><span class="sxs-lookup"><span data-stu-id="c4782-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="c4782-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4782-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="c4782-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c4782-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="c4782-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4782-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4782-109">O valor final definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="c4782-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4782-110">Observações</span><span class="sxs-lookup"><span data-stu-id="c4782-110">Remarks</span></span>

<span data-ttu-id="c4782-111">O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.</span><span class="sxs-lookup"><span data-stu-id="c4782-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="c4782-112">Note-se que o valor final definido de uma gama pode diferir do último elemento na sequência especificada pela gama; por exemplo, num intervalo de 0 ..</span><span class="sxs-lookup"><span data-stu-id="c4782-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="c4782-113">2 ..</span><span class="sxs-lookup"><span data-stu-id="c4782-113">2 ..</span></span> <span data-ttu-id="c4782-114">5 o último elemento é 4, mas o valor final é 5.</span><span class="sxs-lookup"><span data-stu-id="c4782-114">5 the last element is 4 but the end value is 5.</span></span>