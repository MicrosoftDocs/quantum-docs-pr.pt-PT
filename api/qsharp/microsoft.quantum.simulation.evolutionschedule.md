---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: Tipo definido pelo utilizador EvolutionSchedule
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: f99c72a44acc3fdcd9c0f182b51d9437b5e6606d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225300"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="c6bb6-102">Tipo definido pelo utilizador EvolutionSchedule</span><span class="sxs-lookup"><span data-stu-id="c6bb6-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="c6bb6-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c6bb6-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c6bb6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6bb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6bb6-105">Representa um gerador dinâmico dependente do tempo.</span><span class="sxs-lookup"><span data-stu-id="c6bb6-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="c6bb6-106">O `Double` parâmetro é um horário em $[0, 1]$.</span><span class="sxs-lookup"><span data-stu-id="c6bb6-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

