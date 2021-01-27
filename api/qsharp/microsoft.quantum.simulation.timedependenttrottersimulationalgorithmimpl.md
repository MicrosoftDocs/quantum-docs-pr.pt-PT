---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: 3a23c14e8181eeaf1614dab6f8aa5a002364c2b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847811"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="ac366-102">TimeDependentTrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="ac366-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="ac366-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ac366-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ac366-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac366-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac366-105">Implementação de várias etapas Trotter para aproximar um operador unitário que resolve a equação schrödinger dependente do tempo.</span><span class="sxs-lookup"><span data-stu-id="ac366-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac366-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ac366-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="ac366-107">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac366-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac366-108">Duração da evolução do tempo simulada num único passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="ac366-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="ac366-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac366-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac366-110">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="ac366-110">Order of Trotter integrator.</span></span> <span data-ttu-id="ac366-111">Isto deve ser um ou um número par.</span><span class="sxs-lookup"><span data-stu-id="ac366-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="ac366-112">maxTime : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ac366-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ac366-113">Duração total da simulação $t$.</span><span class="sxs-lookup"><span data-stu-id="ac366-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="ac366-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="ac366-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="ac366-115">Uma descrição completa do sistema dependente do tempo a ser simulado.</span><span class="sxs-lookup"><span data-stu-id="ac366-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ac366-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac366-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac366-117">Qubits agidos por simulação.</span><span class="sxs-lookup"><span data-stu-id="ac366-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac366-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac366-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

