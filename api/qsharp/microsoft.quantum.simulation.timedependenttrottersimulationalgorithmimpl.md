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
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a>TimeDependentTrotterSimulationAlgorithmImpl

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementação de várias etapas Trotter para aproximar um operador unitário que resolve a equação schrödinger dependente do tempo.

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="trotterstepsize--double"></a>trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Duração da evolução do tempo simulada num único passo Trotter.


### <a name="trotterorder--int"></a>trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)

Ordem do integrador Trotter. Isto deve ser um ou um número par.


### <a name="maxtime--double"></a>maxTime : [Duplo](xref:microsoft.quantum.lang-ref.double)

Duração total da simulação $t$.


### <a name="evolutionschedule--evolutionschedule"></a>evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)

Uma descrição completa do sistema dependente do tempo a ser simulado.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits agidos por simulação.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

