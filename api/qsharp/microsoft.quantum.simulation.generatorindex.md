---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definido pelo utilizador GeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723901"
---
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="28ff0-102">Tipo definido pelo utilizador GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="28ff0-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="28ff0-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="28ff0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="28ff0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28ff0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28ff0-105">Representa um único termo primitivo no conjunto de todos os geradores dinâmicos, por exemplo, operadores hermitianos, para os quais existe um mapa desse gerador para a evolução temporal por aquele gerador, através `EvolutionSet` de .</span><span class="sxs-lookup"><span data-stu-id="28ff0-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="28ff0-106">O primeiro elemento (Int[], Double[]) é índices que um único termo -- Por exemplo, a cadeia Pauli XXY com coeficiente 0,5 seria indexada por ([1,1,2], [0,5]).</span><span class="sxs-lookup"><span data-stu-id="28ff0-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="28ff0-107">Alternativamente, os hamiltonianos parametrizados por uma variável contínua, como X cos φ + Y sin φ, podem, por exemplo, ser representados por ([], [φ]).</span><span class="sxs-lookup"><span data-stu-id="28ff0-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="28ff0-108">O segundo elemento indexa o subsistema no qual o gerador atua.</span><span class="sxs-lookup"><span data-stu-id="28ff0-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a><span data-ttu-id="28ff0-109">Observações</span><span class="sxs-lookup"><span data-stu-id="28ff0-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="28ff0-110">A interpretação de um `GeneratorIndex` não é definida exceto com referência a um determinado conjunto de geradores.</span><span class="sxs-lookup"><span data-stu-id="28ff0-110">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="28ff0-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="28ff0-111">See Also</span></span>

- [<span data-ttu-id="28ff0-112">Microsoft.Quantum.SimulationSet</span><span class="sxs-lookup"><span data-stu-id="28ff0-112">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="28ff0-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="28ff0-113">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)