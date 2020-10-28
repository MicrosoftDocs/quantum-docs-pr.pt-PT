---
uid: Microsoft.Quantum.Canon.RAll1
title: Operação RAll1
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715623"
---
# <a name="rall1-operation"></a>Operação RAll1

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Realiza uma operação de mudança de fase.

$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="phase--double"></a>fase : [Duplo](xref:microsoft.quantum.lang-ref.double)

A fase $\phi$ aplicada ao estado $\ket{1\cdots 1}\bra{1\cdots 1}$.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O registo cujo estado deve ser rodado por $R dólares.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

