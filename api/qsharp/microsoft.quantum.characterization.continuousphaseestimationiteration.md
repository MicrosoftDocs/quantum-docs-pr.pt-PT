---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operação continuaphaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851896"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="ac913-102">Operação continuaphaseEstimationIteration</span><span class="sxs-lookup"><span data-stu-id="ac913-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="ac913-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ac913-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ac913-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac913-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac913-105">Executa uma única iteração de um algoritmo de estimativa de fase iterativo (controlado clássicamente) usando poderes reais arbitrários de um oráculo unitário.</span><span class="sxs-lookup"><span data-stu-id="ac913-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac913-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ac913-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="ac913-107">oráculo : [Continuarocle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="ac913-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="ac913-108">Operação agindo com duplo $t$ e registo, de tal forma que $U^t$ é aplicado no registo dado, onde $U$ é o unitário cuja fase deve ser estimada, e onde $t$ é o poder inteiro dado ao oráculo</span><span class="sxs-lookup"><span data-stu-id="ac913-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="ac913-109">tempo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac913-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac913-110">Número de vezes para aplicar o oráculo unitário dado.</span><span class="sxs-lookup"><span data-stu-id="ac913-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="ac913-111">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac913-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac913-112">Ângulo para inverter a fase do qubit de controlo antes de agir no estado-alvo.</span><span class="sxs-lookup"><span data-stu-id="ac913-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="ac913-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac913-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac913-114">Registo de estado agido pelo oráculo unitário dado.</span><span class="sxs-lookup"><span data-stu-id="ac913-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="ac913-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac913-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ac913-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac913-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

