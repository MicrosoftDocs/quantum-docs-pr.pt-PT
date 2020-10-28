---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definido pelo utilizador Do Sistema gerador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724559"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="95168-102">Tipo definido pelo utilizador Do Sistema gerador</span><span class="sxs-lookup"><span data-stu-id="95168-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="95168-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="95168-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="95168-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95168-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95168-105">Representa uma coleção de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="95168-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="95168-106">Nós iteramos sobre esta coleção usando um inteiro de índice único, e o tamanho da coleção é assumido como sendo conhecido.</span><span class="sxs-lookup"><span data-stu-id="95168-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="95168-107">Observações</span><span class="sxs-lookup"><span data-stu-id="95168-107">Remarks</span></span>

<span data-ttu-id="95168-108">As instâncias `GeneratorSystem` podem ser definidas facilmente usando a <xref:microsoft.quantum.arrays.lookupfunction> função.</span><span class="sxs-lookup"><span data-stu-id="95168-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="95168-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="95168-109">See Also</span></span>

- [<span data-ttu-id="95168-110">Microsoft.Quantum.Arrays.LookupFunction</span><span class="sxs-lookup"><span data-stu-id="95168-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)