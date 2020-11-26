---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definido pelo utilizador Do Sistema gerador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225232"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="a5ee8-102">Tipo definido pelo utilizador Do Sistema gerador</span><span class="sxs-lookup"><span data-stu-id="a5ee8-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="a5ee8-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a5ee8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a5ee8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5ee8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5ee8-105">Representa uma coleção de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="a5ee8-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="a5ee8-106">Nós iteramos sobre esta coleção usando um inteiro de índice único, e o tamanho da coleção é assumido como sendo conhecido.</span><span class="sxs-lookup"><span data-stu-id="a5ee8-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="a5ee8-107">Observações</span><span class="sxs-lookup"><span data-stu-id="a5ee8-107">Remarks</span></span>

<span data-ttu-id="a5ee8-108">As instâncias `GeneratorSystem` podem ser definidas facilmente usando a <xref:microsoft.quantum.arrays.lookupfunction> função.</span><span class="sxs-lookup"><span data-stu-id="a5ee8-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5ee8-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a5ee8-109">See Also</span></span>

- [<span data-ttu-id="a5ee8-110">Microsoft.Quantum.Arrays.LookupFunction</span><span class="sxs-lookup"><span data-stu-id="a5ee8-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)