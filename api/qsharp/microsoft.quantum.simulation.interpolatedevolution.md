---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Função devolção interpolada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710583"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="87dae-102">Função devolção interpolada</span><span class="sxs-lookup"><span data-stu-id="87dae-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="87dae-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="87dae-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="87dae-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87dae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87dae-105">Interpola entre dois geradores com um horário uniforme, devolvendo uma operação que aplica a evolução simulada sob o gerador dependente do tempo resultante a um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="87dae-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="87dae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="87dae-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="87dae-107">interpolação Hora : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="87dae-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="87dae-108">Hora de fazer a interpolação.</span><span class="sxs-lookup"><span data-stu-id="87dae-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="87dae-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="87dae-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="87dae-110">Gerador inicial para simular a evolução sob.</span><span class="sxs-lookup"><span data-stu-id="87dae-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="87dae-111">EvolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="87dae-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="87dae-112">Gerador final para simular a evolução sob.</span><span class="sxs-lookup"><span data-stu-id="87dae-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="87dae-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="87dae-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="87dae-114">Um algoritmo de simulação dependente do tempo que será usado para simular a evolução durante o calendário uniforme de interpolação.</span><span class="sxs-lookup"><span data-stu-id="87dae-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="87dae-115">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="87dae-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="87dae-116">Observações</span><span class="sxs-lookup"><span data-stu-id="87dae-116">Remarks</span></span>

<span data-ttu-id="87dae-117">Se o tempo de interpolação for escolhido para satisfazer as condições adiabáticas, então esta função devolve uma operação que realiza a preparação do estado adiabático para o gerador dinâmico final.</span><span class="sxs-lookup"><span data-stu-id="87dae-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>