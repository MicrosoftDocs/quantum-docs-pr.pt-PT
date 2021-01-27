---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Medir operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818774"
---
# <a name="measure-operation"></a>Medir operação

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Realiza uma medição articular de um ou mais qubits nas bases pauli especificadas.

O resultado da saída é dado pela distribuição: \start{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket\ \psi \mid| \left|\ boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1\} \end{align} onde $P_i$ é o elemento $i$th de `bases` , e onde $N = \texttt{Length}(\texttt{bases})$.
Ou seja, a medição devolve um `Result` $d$ de modo a que o valor do efeito de medição observado seja $(-1)^d$.

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>Entrada

### <a name="bases--pauli"></a>bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de qubits a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

`Zero` se o $+1$ eigenvalue for observado, e `One` se o $-1$ eigenvalue for observado.

## <a name="remarks"></a>Observações

Se a matriz de base e a matriz de qubits forem diferentes comprimentos, então a operação falhará.