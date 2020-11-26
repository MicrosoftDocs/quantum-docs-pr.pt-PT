---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Tipo definido pelo utilizador EvolutionUnitary
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 38e7da28d4146df9cc132ad69ee939c44bc917f7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225266"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="83395-102">Tipo definido pelo utilizador EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="83395-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="83395-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="83395-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="83395-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83395-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83395-105">Representa um operador unitário de evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="83395-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="83395-106">O primeiro parâmetro é a duração da evolução do tempo, e o segundo parâmetro é o registo qubit agido pelo unitário.</span><span class="sxs-lookup"><span data-stu-id="83395-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

