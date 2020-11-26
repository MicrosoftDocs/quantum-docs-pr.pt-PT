---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: Tipo definido pelo utilizador ContinuousOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226796"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="9ad2c-102">Tipo definido pelo utilizador ContinuousOracle</span><span class="sxs-lookup"><span data-stu-id="9ad2c-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="9ad2c-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9ad2c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9ad2c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ad2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ad2c-105">Representa um oráculo contínuo.</span><span class="sxs-lookup"><span data-stu-id="9ad2c-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="9ad2c-106">Este é um oráculo que implementa $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi (t + \delta t)}} para todos os tempos $t$, onde $U$ é uma operação fixa, e onde $\delta t$ é um número real não negativo.</span><span class="sxs-lookup"><span data-stu-id="9ad2c-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

