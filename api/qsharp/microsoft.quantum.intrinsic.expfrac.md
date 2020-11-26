---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operação ExpFrac
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199000"
---
# <a name="expfrac-operation"></a>Operação ExpFrac

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Aplica o exponencial de um operador pauli multi-qubit com um argumento dado por uma fração diádica.

\start{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} onde $P_i$ é o elemento $i$th de `paulis` , e onde $N = $ `Length(paulis)` .

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.


### <a name="numerator--int"></a>numerador : [Int](xref:microsoft.quantum.lang-ref.int)

Numerador ($k$) na representação da fração dedódica do ângulo pelo qual o registo qubit deve ser rodado.


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

Potência de dois ($n$) especificando o denominador do ângulo pelo qual o registo qubit deve ser rodado.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registe-se para aplicar a rotação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

