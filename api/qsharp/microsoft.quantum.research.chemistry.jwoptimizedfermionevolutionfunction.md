---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Função JWOptimizedFermionEvolution Function
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 952f3dc4ab0595ace0ee34c040cb21969afa111f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710804"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="eae89-102">Função JWOptimizedFermionEvolution Function</span><span class="sxs-lookup"><span data-stu-id="eae89-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="eae89-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="eae89-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="eae89-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eae89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eae89-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="eae89-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="eae89-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="eae89-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="eae89-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="eae89-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="eae89-108">Um índice gerador a ser representado como evolução unitária na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="eae89-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="eae89-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eae89-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eae89-110">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="eae89-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="eae89-111">Saída : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="eae89-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="eae89-112">Uma `EvolutionUnitary` evolução temporal representando o termo referenciado em 'generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="eae89-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>