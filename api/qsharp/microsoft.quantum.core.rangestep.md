---
uid: Microsoft.Quantum.Core.RangeStep
title: Função RangeStep
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713159"
---
# <a name="rangestep-function"></a><span data-ttu-id="48888-102">Função RangeStep</span><span class="sxs-lookup"><span data-stu-id="48888-102">RangeStep function</span></span>

<span data-ttu-id="48888-103">Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="48888-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="48888-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48888-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48888-105">Devolve o inteiro que especifica como o próximo valor de uma gama é calculado.</span><span class="sxs-lookup"><span data-stu-id="48888-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="48888-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="48888-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="48888-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="48888-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="48888-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48888-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48888-109">O valor de passo definido da gama dada.</span><span class="sxs-lookup"><span data-stu-id="48888-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="48888-110">Observações</span><span class="sxs-lookup"><span data-stu-id="48888-110">Remarks</span></span>

<span data-ttu-id="48888-111">O primeiro elemento de uma expressão de alcance é `start` , o seu segundo elemento é , terceiro elemento é , `start+step` `start+step+step` etc., até `end` ser passado.</span><span class="sxs-lookup"><span data-stu-id="48888-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>