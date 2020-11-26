---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Aplicar operaçãoPauliFromBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: cf4c99ec5134fac788cdd4c8a057258790152a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209065"
---
# <a name="applypaulifrombitstring-operation"></a>Aplicar operaçãoPauliFromBitString

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica um operador Pauli em cada qubit numa matriz se a parte correspondente de uma matriz Boolean corresponder a uma determinada entrada.

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operador Pauli para aplicar a `qubits[idx]` onde `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)

aplicar Pauli se bit é este valor


### <a name="bits--bool"></a>bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Registo booleano especificando qual o qubit correspondente `qubits` em deve ser operado em


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo quântico no qual aplicar seletivamente o operador pauli especificado



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A matriz booleana e o registo quântico devem ter o mesmo comprimento.