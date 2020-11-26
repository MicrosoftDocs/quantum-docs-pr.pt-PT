---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: operação _flipToBasis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223991"
---
# <a name="_fliptobasis-operation"></a>operação _flipToBasis

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Aplica unidades que mapeiam $\ket {0} \otimes\cdots\ket {0} $ a $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, onde $\ket{\psi_k}$ depende `basis[k]` de .

A correspondência entre o valor de `basis[k]` e $\ket{\psi_k}$ é o seguinte:

- `basis[k]=0` $\rightarrow \ket {0} $.
- `basis[k]=1` $\rightarrow \ket {1} $.
- `basis[k]=2` $\rightarrow \ket{+}$.
- `basis[k]=3` $\rightarrow \ket{i}$ (+1 eigenstate de Pauli Y ).

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="basis--int"></a>base : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de IDs de base de um único qubit (0 <= id <= 3), um para cada elemento de qubits.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit para ser operado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

