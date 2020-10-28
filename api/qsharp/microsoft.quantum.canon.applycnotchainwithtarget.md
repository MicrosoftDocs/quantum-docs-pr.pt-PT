---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: Aplicação Operação TNOTChainWithTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718366"
---
# <a name="applycnotchainwithtarget-operation"></a>Aplicação Operação TNOTChainWithTarget

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Calcula a paridade de uma matriz de qubits num qubit alvo.

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a>Descrição

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