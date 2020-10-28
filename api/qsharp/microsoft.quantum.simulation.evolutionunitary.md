---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Tipo definido pelo utilizador EvolutionUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724853"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="feecd-102">Tipo definido pelo utilizador EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="feecd-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="feecd-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="feecd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="feecd-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="feecd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="feecd-105">Representa um operador unitário de evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="feecd-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="feecd-106">O primeiro parâmetro é a duração da evolução do tempo, e o segundo parâmetro é o registo qubit agido pelo unitário.</span><span class="sxs-lookup"><span data-stu-id="feecd-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

