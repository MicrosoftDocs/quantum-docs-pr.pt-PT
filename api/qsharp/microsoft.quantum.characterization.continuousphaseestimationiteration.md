---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: Operação continuaphaseEstimationIteration
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 925b9040f6d9cda074b18a6f9079ccb653f9fa98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851896"
---
# <a name="continuousphaseestimationiteration-operation"></a>Operação continuaphaseEstimationIteration

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa uma única iteração de um algoritmo de estimativa de fase iterativo (controlado clássicamente) usando poderes reais arbitrários de um oráculo unitário.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
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

