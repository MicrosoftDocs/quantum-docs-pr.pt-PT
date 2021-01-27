---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: Função PauliEvolutionFunction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 9b12dc4a05c99aad319799f8c6526cd3085e6dcd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847972"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="a12d4-102">Função PauliEvolutionFunction</span><span class="sxs-lookup"><span data-stu-id="a12d4-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="a12d4-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a12d4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a12d4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a12d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a12d4-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="a12d4-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="a12d4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a12d4-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="a12d4-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a12d4-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a12d4-108">Um índice gerador a ser representado como evolução unitária na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="a12d4-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="a12d4-109">Saída : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="a12d4-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="a12d4-110">Uma `EvolutionUnitary` evolução temporal representando o termo referenciado em 'generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="a12d4-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>