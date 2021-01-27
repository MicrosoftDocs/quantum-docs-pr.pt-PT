---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: Operação TrotterStepImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 33dc922cd5a60590a1306369fb99615fc6575b22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856736"
---
# <a name="trotterstepimpl-operation"></a>Operação TrotterStepImpl

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa a evolução temporal por um termo contido num `GeneratorSystem` .

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="evolutiongenerator--evolutiongenerator"></a>EvolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

Uma descrição completa do sistema a ser simulado.


### <a name="idx--int"></a>idx : [Int](xref:microsoft.quantum.lang-ref.int)

Índice inteiro para um termo no sistema descrito.


### <a name="stepsize--double"></a>stepsize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Multiplicador sobre a duração da evolução do tempo por termo indexado por `idx` .


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits agidos por simulação.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

