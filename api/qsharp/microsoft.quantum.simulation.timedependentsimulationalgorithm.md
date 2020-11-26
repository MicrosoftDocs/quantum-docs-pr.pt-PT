---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TempoDependentSimulationAlgorithm tipo definido do utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192524"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="99f61-102">TempoDependentSimulationAlgorithm tipo definido do utilizador</span><span class="sxs-lookup"><span data-stu-id="99f61-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="99f61-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="99f61-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="99f61-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99f61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99f61-105">Representa um algoritmo de simulação dependente do tempo.</span><span class="sxs-lookup"><span data-stu-id="99f61-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="99f61-106">Uma técnica de simulação dependente do tempo converte um <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="99f61-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="99f61-107">para a evolução do tempo unitário para algum intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="99f61-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

