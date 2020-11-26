---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Aplicação Operação TNOTChainWithTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219112"
---
# <a name="applycnotchainwithtarget-operation"></a>Aplicação Operação TNOTChainWithTarget

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula a paridade de uma matriz de qubits num qubit alvo.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Se a matriz estiver inicialmente no estado $\ket{q_0} \ket{q_1} \cdots \ket{{q_{text{target}}}$, o estado final é dado por $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{text{target}}}.}}..}$..} \oplus \cdots \oplus q_0 \oplus q_{text{target}}}..}..}.".

## <a name="input"></a>Entrada

### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matriz de qubits em que a paridade é calculada.


### <a name="targetqubit--qubit"></a>targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit final em que a paridade de 'qubits' é XORed.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

e

```qsharp
ApplyCNOTChain(qs);
```