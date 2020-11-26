---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: Função devolção interpolada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 2ad907c02a2412dd4bf95630f401b5f1db5c8a08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225113"
---
# <a name="interpolatedevolution-function"></a>Função devolção interpolada

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interpola entre dois geradores com um horário uniforme, devolvendo uma operação que aplica a evolução simulada sob o gerador dependente do tempo resultante a um registo qubit.

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="interpolationtime--double"></a>interpolação Hora : [Duplo](xref:microsoft.quantum.lang-ref.double)

Hora de fazer a interpolação.


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Gerador inicial para simular a evolução sob.


### <a name="evolutiongeneratorend--evolutiongenerator"></a>EvolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Gerador final para simular a evolução sob.


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

Um algoritmo de simulação dependente do tempo que será usado para simular a evolução durante o calendário uniforme de interpolação.



## <a name="output--qubit--unit--is-adj--ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl



## <a name="remarks"></a>Observações

Se o tempo de interpolação for escolhido para satisfazer as condições adiabáticas, então esta função devolve uma operação que realiza a preparação do estado adiabático para o gerador dinâmico final.