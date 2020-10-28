---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Operação TrotterStepImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725326"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="8a33c-102">Operação TrotterStepImpl</span><span class="sxs-lookup"><span data-stu-id="8a33c-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="8a33c-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8a33c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8a33c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a33c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a33c-105">Implementa a evolução temporal por um termo contido num `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="8a33c-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8a33c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a33c-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="8a33c-107">EvolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="8a33c-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="8a33c-108">Uma descrição completa do sistema a ser simulado.</span><span class="sxs-lookup"><span data-stu-id="8a33c-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="8a33c-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8a33c-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8a33c-110">Índice inteiro para um termo no sistema descrito.</span><span class="sxs-lookup"><span data-stu-id="8a33c-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="8a33c-111">stepsize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8a33c-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8a33c-112">Multiplicador sobre a duração da evolução do tempo por termo indexado por `idx` .</span><span class="sxs-lookup"><span data-stu-id="8a33c-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="8a33c-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a33c-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8a33c-114">Qubits agidos por simulação.</span><span class="sxs-lookup"><span data-stu-id="8a33c-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a33c-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a33c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

