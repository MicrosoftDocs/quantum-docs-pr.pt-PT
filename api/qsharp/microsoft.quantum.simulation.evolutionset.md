---
uid: Microsoft.Quantum.Simulation.EvolutionSet
title: Tipo definido pelo utilizador EvolutionSet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSet
qsharp.summary: >-
  Represents a set of gates that can be readily implemented and used to implement simulation algorithms.

  Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time
ms.openlocfilehash: 35c0b24da284a5871fd11b6d624102b853b89d19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856061"
---
# <a name="evolutionset-user-defined-type"></a><span data-ttu-id="04c37-102">Tipo definido pelo utilizador EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="04c37-102">EvolutionSet user defined type</span></span>

<span data-ttu-id="04c37-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="04c37-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="04c37-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04c37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04c37-105">Representa um conjunto de portas que podem ser facilmente implementados e usados para implementar algoritmos de simulação.</span><span class="sxs-lookup"><span data-stu-id="04c37-105">Represents a set of gates that can be readily implemented and used to implement simulation algorithms.</span></span>

<span data-ttu-id="04c37-106">Os elementos do conjunto são indexados por um  <xref:microsoft.quantum.simulation.generatorindex> , e cada conjunto é descrito por uma função de `GeneratorIndex` , que são  <xref:microsoft.quantum.simulation.evolutionunitary> operações parametrizadas por um número real que representa o tempo</span><span class="sxs-lookup"><span data-stu-id="04c37-106">Elements in the set are indexed by a  <xref:microsoft.quantum.simulation.generatorindex>, and each set is described by a function from `GeneratorIndex` to  <xref:microsoft.quantum.simulation.evolutionunitary>, which are operations parameterized by a real number representing time</span></span>

```qsharp

newtype EvolutionSet = ((Microsoft.Quantum.Simulation.GeneratorIndex -> Microsoft.Quantum.Simulation.EvolutionUnitary));
```

