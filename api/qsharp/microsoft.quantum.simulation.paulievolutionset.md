---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: Função PauliEvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722050"
---
# <a name="paulievolutionset-function"></a><span data-ttu-id="86b88-102">Função PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="86b88-102">PauliEvolutionSet function</span></span>

<span data-ttu-id="86b88-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="86b88-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="86b88-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86b88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86b88-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="86b88-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a><span data-ttu-id="86b88-106">Saída : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span><span class="sxs-lookup"><span data-stu-id="86b88-106">Output : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)</span></span>

<span data-ttu-id="86b88-107">Um `EvolutionSet` que mapeia uma `GeneratorIndex` base de Pauli para um "EvolutionUnitary".</span><span class="sxs-lookup"><span data-stu-id="86b88-107">An `EvolutionSet` that maps a `GeneratorIndex` for the Pauli basis to an \`EvolutionUnitary.</span></span>

## <a name="remarks"></a><span data-ttu-id="86b88-108">Observações</span><span class="sxs-lookup"><span data-stu-id="86b88-108">Remarks</span></span>

<span data-ttu-id="86b88-109">Isto é obtido por aplicação parcial de <xref:microsoft.quantum.simulation.paulievolutionfunction> .</span><span class="sxs-lookup"><span data-stu-id="86b88-109">This is obtained by partial application of <xref:microsoft.quantum.simulation.paulievolutionfunction>.</span></span>