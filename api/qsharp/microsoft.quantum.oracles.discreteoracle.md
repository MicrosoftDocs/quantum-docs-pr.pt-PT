---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Tipo definido pelo utilizador DiscreteOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842579"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="acbbb-102">Tipo definido pelo utilizador DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="acbbb-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="acbbb-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="acbbb-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="acbbb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acbbb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acbbb-105">Representa um oráculo discreto.</span><span class="sxs-lookup"><span data-stu-id="acbbb-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="acbbb-106">Este é um oráculo que implementa $U^m$ para uma operação fixa $U$ e um inteiro não negativo $m$.</span><span class="sxs-lookup"><span data-stu-id="acbbb-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

