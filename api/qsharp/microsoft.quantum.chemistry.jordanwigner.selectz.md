---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operação SelectZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224722"
---
# <a name="selectz-operation"></a>Operação SelectZ

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Um $U$ unitário que aplica o portão Pauli $Z$ em um qubits $p$ condicionados em um estado de índice $\ket{p}$. Ou seja, $$ \start{align} U\ket{p}\ket{\psi} = \ket{p}Z \_ p\ket{\psi} \end{align} $$

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O estado $\ket{p}$ deste registo determina o qubit em que $Z$ é aplicado.


### <a name="targetregister--qubit"></a>targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de qubits em que são aplicados os operadores Pauli.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

