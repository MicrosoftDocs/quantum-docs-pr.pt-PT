---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Operação TrotterStepImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: bc6c3c6656da319fce9c7c48824dbc4ad75ccc83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203421"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="5d2a9-102">Operação TrotterStepImpl</span><span class="sxs-lookup"><span data-stu-id="5d2a9-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="5d2a9-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5d2a9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5d2a9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d2a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d2a9-105">Implementa a evolução temporal por um termo contido num `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="5d2a9-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5d2a9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5d2a9-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="5d2a9-107">EvolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="5d2a9-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="5d2a9-108">Uma descrição completa do sistema a ser simulado.</span><span class="sxs-lookup"><span data-stu-id="5d2a9-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="5d2a9-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d2a9-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d2a9-110">Índice inteiro para um termo no sistema descrito.</span><span class="sxs-lookup"><span data-stu-id="5d2a9-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5d2a9-111">stepsize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d2a9-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d2a9-112">Multiplicador sobre a duração da evolução do tempo por termo indexado por `idx` .</span><span class="sxs-lookup"><span data-stu-id="5d2a9-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5d2a9-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5d2a9-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5d2a9-114">Qubits agidos por simulação.</span><span class="sxs-lookup"><span data-stu-id="5d2a9-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d2a9-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d2a9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

