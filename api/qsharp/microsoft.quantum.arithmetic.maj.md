---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operação MAJ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721018"
---
# <a name="maj-operation"></a>Operação MAJ

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Isto aplica a operação de maioria no local a 3 qubits.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Descrição

Se denotarmos o estado do qubit alvo como $\ket{z}$, e os estados de entrada dos qubits de entrada como $\ket{x}$ e $\ket{y}$, então esta operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}}

## <a name="input"></a>Entrada

### <a name="input0--qubit"></a>input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O primeiro qubit de entrada.


### <a name="input1--qubit"></a>input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O segundo qubit de entrada.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit no qual será aplicada a função maioritária.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

