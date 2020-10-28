---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: Tipo definido pelo utilizador DiscreteOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724923"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="667c3-102">Tipo definido pelo utilizador DiscreteOracle</span><span class="sxs-lookup"><span data-stu-id="667c3-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="667c3-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="667c3-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="667c3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="667c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="667c3-105">Representa um oráculo discreto.</span><span class="sxs-lookup"><span data-stu-id="667c3-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="667c3-106">Este é um oráculo que implementa $U^m$ para uma operação fixa $U$ e um inteiro não negativo $m$.</span><span class="sxs-lookup"><span data-stu-id="667c3-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

