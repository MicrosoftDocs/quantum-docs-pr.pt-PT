---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operação TrotterSimulationAlgorithmImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: b2411950b90eb676b1da53bd06bde648099e2db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858895"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="bc132-102">Operação TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="bc132-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="bc132-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bc132-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bc132-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc132-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc132-105">Faz chamadas repetidas `TrotterStep` para aproximar o operador de evolução temporal _exp.-iHt_.</span><span class="sxs-lookup"><span data-stu-id="bc132-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bc132-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bc132-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="bc132-107">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bc132-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bc132-108">Duração da evolução do tempo simulada num único passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="bc132-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="bc132-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc132-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc132-110">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="bc132-110">Order of Trotter integrator.</span></span> <span data-ttu-id="bc132-111">Isto deve ser um ou um número par.</span><span class="sxs-lookup"><span data-stu-id="bc132-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="bc132-112">maxTime : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bc132-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bc132-113">Duração total da simulação $t$.</span><span class="sxs-lookup"><span data-stu-id="bc132-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="bc132-114">EvolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="bc132-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="bc132-115">Uma descrição completa do sistema a ser simulado.</span><span class="sxs-lookup"><span data-stu-id="bc132-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bc132-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bc132-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bc132-117">Qubits agidos por simulação.</span><span class="sxs-lookup"><span data-stu-id="bc132-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc132-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc132-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

