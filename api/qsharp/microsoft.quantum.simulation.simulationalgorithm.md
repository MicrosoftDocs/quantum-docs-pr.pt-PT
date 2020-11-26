---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: Tipo definido pelo utilizador SimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 2f340492b51c97e353cc071d6d563a30a1db86d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192439"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="25399-102">Tipo definido pelo utilizador SimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="25399-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="25399-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="25399-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="25399-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25399-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25399-105">Representa um algoritmo de simulação independente do tempo.</span><span class="sxs-lookup"><span data-stu-id="25399-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="25399-106">Uma técnica de simulação independente do tempo converte um <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="25399-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="25399-107">para a evolução do tempo unitário para algum intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="25399-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

