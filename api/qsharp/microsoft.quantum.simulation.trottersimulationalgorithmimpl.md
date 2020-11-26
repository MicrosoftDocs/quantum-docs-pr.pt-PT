---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operação TrotterSimulationAlgorithmImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203405"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="17d72-102">Operação TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="17d72-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="17d72-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="17d72-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="17d72-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17d72-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17d72-105">Faz chamadas repetidas `TrotterStep` para aproximar o operador de evolução temporal _exp.-iHt_.</span><span class="sxs-lookup"><span data-stu-id="17d72-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="17d72-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="17d72-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="17d72-107">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17d72-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17d72-108">Duração da evolução do tempo simulada num único passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="17d72-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="17d72-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="17d72-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="17d72-110">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="17d72-110">Order of Trotter integrator.</span></span> <span data-ttu-id="17d72-111">Isto deve ser um ou um número par.</span><span class="sxs-lookup"><span data-stu-id="17d72-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="17d72-112">maxTime : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17d72-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17d72-113">Duração total da simulação $t$.</span><span class="sxs-lookup"><span data-stu-id="17d72-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="17d72-114">EvolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="17d72-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="17d72-115">Uma descrição completa do sistema a ser simulado.</span><span class="sxs-lookup"><span data-stu-id="17d72-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="17d72-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="17d72-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="17d72-117">Qubits agidos por simulação.</span><span class="sxs-lookup"><span data-stu-id="17d72-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17d72-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17d72-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

