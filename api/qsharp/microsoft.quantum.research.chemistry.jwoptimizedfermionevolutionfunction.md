---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Função JWOptimizedFermionEvolution Function
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: d70bea8fcb5bd82ddad6dcd2b67c3eb178283bb3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857871"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="fe906-102">Função JWOptimizedFermionEvolution Function</span><span class="sxs-lookup"><span data-stu-id="fe906-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="fe906-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fe906-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="fe906-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fe906-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="fe906-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="fe906-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="fe906-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fe906-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="fe906-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fe906-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fe906-108">Um índice gerador a ser representado como evolução unitária na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="fe906-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="fe906-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe906-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe906-110">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="fe906-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="fe906-111">Saída : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="fe906-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="fe906-112">Uma `EvolutionUnitary` evolução temporal representando o termo referenciado em 'generatorIndex.</span><span class="sxs-lookup"><span data-stu-id="fe906-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>