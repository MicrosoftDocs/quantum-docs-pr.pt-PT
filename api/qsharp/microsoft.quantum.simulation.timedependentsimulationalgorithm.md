---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TempoDependentSimulationAlgorithm tipo definido do utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 4f393c958e686f2ded3bf3372ff9fd52b2a363cd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854129"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="2ef8b-102">TempoDependentSimulationAlgorithm tipo definido do utilizador</span><span class="sxs-lookup"><span data-stu-id="2ef8b-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="2ef8b-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2ef8b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ef8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ef8b-105">Representa um algoritmo de simulação dependente do tempo.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="2ef8b-106">Uma técnica de simulação dependente do tempo converte um <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="2ef8b-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="2ef8b-107">para a evolução do tempo unitário para algum intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="2ef8b-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

