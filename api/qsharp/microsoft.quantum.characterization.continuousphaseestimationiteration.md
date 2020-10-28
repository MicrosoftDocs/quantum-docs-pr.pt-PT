---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operação continuaphaseEstimationIteration
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715077"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operação continuaphaseEstimationIteration

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [](https://nuget.org/packages/)


Executa uma única iteração de um algoritmo de estimativa de fase iterativo (controlado clássicamente) usando poderes reais arbitrários de um oráculo unitário.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="oracle--continuousoracle"></a>oráculo : [Continuarocle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operação agindo com duplo $t$ e registo, de tal forma que $U^t$ é aplicado no registo dado, onde $U$ é o unitário cuja fase deve ser estimada, e onde $t$ é o poder inteiro dado ao oráculo


### <a name="time--double"></a>tempo : [Duplo](xref:microsoft.quantum.lang-ref.double)

Número de vezes para aplicar o oráculo unitário dado.


### <a name="theta--double"></a>theta : [Duplo](xref:microsoft.quantum.lang-ref.double)

Ângulo para inverter a fase do qubit de controlo antes de agir no estado-alvo.


### <a name="targetstate--qubit"></a>targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de estado agido pelo oráculo unitário dado.


### <a name="controlqubit--qubit"></a>controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

