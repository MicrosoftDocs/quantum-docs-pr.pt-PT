---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: AplicarOperaçãoPartition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: f36bccb727bb38a0cdf4f1fedabc9f3f554059ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208402"
---
# <a name="applytopartition-operation"></a>AplicarOperaçãoPartition

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica um par de operações a uma determinada divisão de um registo em duas partes.

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubit--unit"></a>op :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [unidade](xref:microsoft.quantum.lang-ref.unit)> 

O par de operações a aplicar à partição dada.


### <a name="numberofqubitstofirstargument--int"></a>númeroOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)

Número de qubits do alvo para colocar na primeira parte da partição.
Os qubits restantes constituem a segunda parte da partição.


### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits que estão a ser divididos e operados pela operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToPartitionA](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Microsoft.Quantum.Canon.ApplyToPartitionC](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Microsoft.Quantum.Canon.ApplyToPartitionCA](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)