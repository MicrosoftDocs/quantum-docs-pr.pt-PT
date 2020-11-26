---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operação QuantumPhaseEstimation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 14ba3e012f6561e7089f9fe59b2a13516b211d51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204220"
---
# <a name="quantumphaseestimation-operation"></a>Operação QuantumPhaseEstimation

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa o algoritmo de estimativa da fase quântica para um dado oráculo `U` `targetState` e, lendo a fase num registo quântico de grande ponta.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="oracle--discreteoracle"></a>oráculo : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Uma operação que implementa $U^m$ para dados poderes inteiros m.


### <a name="targetstate--qubit"></a>targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo quântico que representa o estado $\ket{\phi}$ agido por $U$. Se $\ket{\phi}$ é um eigenstate de $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ por $\phi \in [0, 2\pi)$ uma fase desconhecida.


### <a name="controlregister--bigendian"></a>controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Um registo inteiro de representação de grande ponta que pode ser usado para controlar o oráculo fornecido, e que conterá a representação de $\phi$ após a aplicação desta operação. Presume-se que o controlRegister comece no estado inicial $\ket{00\cdots 0}$, onde o comprimento do registo indica a precisão desejada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

