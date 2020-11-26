---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223702"
---
# <a name="assertprobint-operation"></a>AssertProbInt

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que a probabilidade de um estado específico de um registo quântico tem o valor esperado.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Description

Dado um $n$-qubit estado quântico $\ket{\psi}=\sum^{2^n-1}___j=0}\alpha_j \ket{j}$, afirma que a probabilidade $\alpha_j^2$ do estado $\ket{j}$ indexado por $j$ tem o valor esperado.

## <a name="input"></a>Entrada

### <a name="stateindex--int"></a>estadoIndex : [Int](xref:microsoft.quantum.lang-ref.int)

O índice $j$ do estado $\ket{j}$ representado por um `LittleEndian` registo.


### <a name="expected--double"></a>esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)

O valor esperado de $\alpha_j^2$.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O registo qubit que armazena $\ket{\psi}$ em formato pequeno-endian.


### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

Tolerância absoluta na diferença entre real e esperado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

