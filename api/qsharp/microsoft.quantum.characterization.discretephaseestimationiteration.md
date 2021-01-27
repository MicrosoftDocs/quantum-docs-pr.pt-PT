---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: Operação de estimação de Fases Discretas
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 03e2300dcc2d2cb42992e074833c8cd2530e898b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839965"
---
# <a name="discretephaseestimationiteration-operation"></a>Operação de estimação de Fases Discretas

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa uma única iteração de um algoritmo de estimativa de fase iterativo (controlado clássicamente) usando poderes inteiros de um oráculo unitário.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="oracle--discreteoracle"></a>oráculo : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operação agindo num número inteiro e num registo, de tal forma que $U^m$ é aplicado ao registo dado, onde $U$ é o unitário cuja fase deve ser estimada, e onde $m$ é o poder inteiro dado ao oráculo


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

Número de vezes para aplicar o oráculo unitário dado.


### <a name="theta--double"></a>theta : [Duplo](xref:microsoft.quantum.lang-ref.double)

Ângulo para inverter a fase do qubit de controlo antes de agir no estado-alvo.


### <a name="targetstate--qubit"></a>targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de estado agido pelo oráculo unitário dado.


### <a name="controlqubit--qubit"></a>controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit auxiliar usado para controlar a aplicação do oráculo dado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

