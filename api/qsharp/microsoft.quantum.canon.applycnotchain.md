---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: Aplicação OperaçãoCNOTChain
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: b5a74eb66529095233c89a4ec7ea37c996458cb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841952"
---
# <a name="applycnotchain-operation"></a>Aplicação OperaçãoCNOTChain

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula a paridade de um registo de qubits no lugar.

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação transforma o estado da sua entrada como $$ \start{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \000 {q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}}
\end{align} $$

## <a name="input"></a>Entrada

### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Matriz de qubits cuja paridade deve ser calculada e armazenada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

