---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operação SelectZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713789"
---
# <a name="selectz-operation"></a>Operação SelectZ

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Um $U$ unitário que aplica o portão Pauli $Z$ em um qubits $p$ condicionados em um estado de índice $\ket{p}$. Ou seja, $$ \start{align} U\ket{p}\ket{\psi} = \ket{p}Z \_ p\ket{\psi} \end{align} $$

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O estado $\ket{p}$ deste registo determina o qubit em que $Z$ é aplicado.


### <a name="targetregister--qubit"></a>targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de qubits em que são aplicados os operadores Pauli.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

