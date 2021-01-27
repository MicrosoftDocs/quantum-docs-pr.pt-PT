---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843406"
---
# <a name="assertprobint-operation"></a>AssertProbInt

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que a probabilidade de um estado específico de um registo quântico tem o valor esperado.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Descrição

Dado um $n$-qubit estado quântico $\ket{\psi}=\sum^{2^n-1}_j=0}\alpha_j \ket{j}$, afirma que a probabilidade $|\alpha_j|^2$ do estado $\ket{j}} indexado por $j$ tem o valor esperado.

## <a name="input"></a>Entrada

### <a name="stateindex--int"></a>estadoIndex : [Int](xref:microsoft.quantum.lang-ref.int)

O índice $j$ do estado $\ket{j}$ representado por um `LittleEndian` registo.


### <a name="expected--double"></a>esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)

O valor esperado de $|\alpha_j|^2$.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O registo qubit que armazena $\ket{\psi}$ em formato pequeno-endian.


### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

Tolerância absoluta na diferença entre real e esperado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

Suponha que o `qubits` registo codifica um estado quântico de 3 qubits $\ket{\psi}=\sqrt{1/8}\ket {0} +\sqrt{7/8}\ket {6} $ em formato pequeno-endian.
Isto significa que o número diz $\ket {0} \equiv\ket {0} {0} \ket \ket {0} \ket $ e $\ket {6} \equiv\ket {0} {1} \ket \ket \ket {1} \ket $. Em seguida, as seguintes afirmações sucedem- se:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```