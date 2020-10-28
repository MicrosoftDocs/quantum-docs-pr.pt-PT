---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TempoDependentSimulationAlgorithm tipo definido do utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725749"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a>TempoDependentSimulationAlgorithm tipo definido do utilizador

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Representa um algoritmo de simulação dependente do tempo.

Uma técnica de simulação dependente do tempo converte um <xref:microsoft.quantum.simulation.evolutionschedule>
para a evolução do tempo unitário para algum intervalo de tempo.

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

