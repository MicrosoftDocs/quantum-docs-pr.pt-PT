---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operação MAJ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222767"
---
# <a name="maj-operation"></a>Operação MAJ

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Isto aplica a operação de maioria no local a 3 qubits.

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Se denotarmos o estado do qubit alvo como $\ket{z}$, e os estados de entrada dos qubits de entrada como $\ket{x}$ e $\ket{y}$, então esta operação executa a seguinte transformação: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}}

## <a name="input"></a>Entrada

### <a name="input0--qubit"></a>input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O primeiro qubit de entrada.


### <a name="input1--qubit"></a>input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O segundo qubit de entrada.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit no qual será aplicada a função maioritária.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

