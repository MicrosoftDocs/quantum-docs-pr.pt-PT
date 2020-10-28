---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Aplicar a operação DoPartitionC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717118"
---
# <a name="applytopartitionc-operation"></a>Aplicar a operação DoPartitionC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica um par de operações a uma determinada divisão de um registo em duas partes.
O modificador `C` indica que a operação é controlável.

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubit--unit-ctl"></a>op :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl

O par de operações a aplicar à partição dada.


### <a name="numberofqubitstofirstargument--int"></a>númeroOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)

Número de qubits do alvo para colocar na primeira parte da partição.
Os qubits restantes constituem a segunda parte da partição.


### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits que estão a ser divididos e operados pela operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)