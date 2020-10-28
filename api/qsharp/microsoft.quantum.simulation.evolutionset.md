---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definido pelo utilizador EvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 41504837b281b1021a2d09ef75acc10315b4fd07
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710611"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="533f2-102">Tipo definido pelo utilizador EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="533f2-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="533f2-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="533f2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="533f2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="533f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="533f2-105">Representa um conjunto de portas que podem ser facilmente implementados e usados para implementar algoritmos de simulação.</span><span class="sxs-lookup"><span data-stu-id="533f2-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="533f2-106">Os elementos do conjunto são indexados por um  <xref:microsoft.quantum.simulation.generatorindex> , e cada conjunto é descrito por uma função de `GeneratorIndex` , que são  <xref:microsoft.quantum.simulation.evolutionunitary> operações parametrizadas por um número real que representa o tempo</span><span class="sxs-lookup"><span data-stu-id="533f2-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

