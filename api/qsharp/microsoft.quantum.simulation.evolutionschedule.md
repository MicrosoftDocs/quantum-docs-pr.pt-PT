---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: Tipo definido pelo utilizador EvolutionSchedule
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 4dc8bf4028e82d3e746779ae8c7d400dcbd3ea1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710622"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="dea36-102">Tipo definido pelo utilizador EvolutionSchedule</span><span class="sxs-lookup"><span data-stu-id="dea36-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="dea36-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dea36-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dea36-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dea36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dea36-105">Representa um gerador dinâmico dependente do tempo.</span><span class="sxs-lookup"><span data-stu-id="dea36-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="dea36-106">O `Double` parâmetro é um horário em $[0, 1]$.</span><span class="sxs-lookup"><span data-stu-id="dea36-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

