---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operação continuaphaseEstimationIteration
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216290"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="51b4d-102">Operação continuaphaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="51b4d-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="51b4d-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="51b4d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="51b4d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51b4d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51b4d-105">Executa uma única iteração de um algoritmo de estimativa de fase iterativo (controlado clássicamente) usando poderes reais arbitrários de um oráculo unitário.</span><span class="sxs-lookup"><span data-stu-id="51b4d-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="51b4d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="51b4d-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="51b4d-107">oráculo : [Continuarocle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="51b4d-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="51b4d-108">Operação agindo com duplo $t$ e registo, de tal forma que $U^t$ é aplicado no registo dado, onde $U$ é o unitário cuja fase deve ser estimada, e onde $t$ é o poder inteiro dado ao oráculo</span><span class="sxs-lookup"><span data-stu-id="51b4d-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="51b4d-109">tempo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="51b4d-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="51b4d-110">Número de vezes para aplicar o oráculo unitário dado.</span><span class="sxs-lookup"><span data-stu-id="51b4d-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="51b4d-111">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="51b4d-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="51b4d-112">Ângulo para inverter a fase do qubit de controlo antes de agir no estado-alvo.</span><span class="sxs-lookup"><span data-stu-id="51b4d-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="51b4d-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="51b4d-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="51b4d-114">Registo de estado agido pelo oráculo unitário dado.</span><span class="sxs-lookup"><span data-stu-id="51b4d-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="51b4d-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="51b4d-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="51b4d-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51b4d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

