---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Função RangeAsIntArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713366"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="08498-102">Função RangeAsIntArray</span><span class="sxs-lookup"><span data-stu-id="08498-102">RangeAsIntArray function</span></span>

<span data-ttu-id="08498-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="08498-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="08498-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08498-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08498-105">Cria uma série `arr` de inteiros enumerados pelo início. passo. fim.</span><span class="sxs-lookup"><span data-stu-id="08498-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="08498-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="08498-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="08498-107">gama : [Gama](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="08498-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="08498-108">A `Range` de valores `start..step..end` a converter para uma matriz.</span><span class="sxs-lookup"><span data-stu-id="08498-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="08498-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="08498-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="08498-110">Uma nova gama de inteiros que corresponde aos valores iterados por `range` .</span><span class="sxs-lookup"><span data-stu-id="08498-110">A new array of integers corresponding to values iterated over by `range`.</span></span>