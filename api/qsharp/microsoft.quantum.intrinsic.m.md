---
uid: Microsoft.Quantum.Intrinsic.M
title: Operação M
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212346"
---
# <a name="m-operation"></a>Operação M

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Executa uma medição de um único qubit na base Pauli $Z$.

O resultado da saída é dado pela distribuição \start{align} \Pr (\texttt{Zero} / \ket{\psi}) = \braket{\psi [ travão{0] \braket{0 / \psi}.
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>Entrada

### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

`Zero` se o $+1$ eigenvalue for observado, e `One` se o $-1$ eigenvalue for observado.

## <a name="remarks"></a>Observações

Equivalente a:

```qsharp
Measure([PauliZ], [qubit]);
```