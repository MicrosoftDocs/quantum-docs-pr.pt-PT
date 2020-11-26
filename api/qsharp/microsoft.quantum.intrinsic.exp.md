---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operação Exp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212414"
---
# <a name="exp-operation"></a>Operação Exp

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Aplica o exponencial de um operador pauli multi-qubit.

\start{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}} \end{align} onde $P_i$ é o elemento $i$th de `paulis` , e onde $N = $ `Length(paulis)` .

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.


### <a name="theta--double"></a>theta : [Duplo](xref:microsoft.quantum.lang-ref.double)

Ângulo sobre o operador pauli multi-qubit dado pelo qual o registo-alvo deve ser rodado.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registe-se para aplicar a rotação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

