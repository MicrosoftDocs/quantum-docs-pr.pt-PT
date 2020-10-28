---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Preparar operaçãoQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723005"
---
# <a name="preparequbit-operation"></a>Preparar operaçãoQubit

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Prepara um qubit no estado `Zero` +1 ( ) do operador Pauli.
Se o operador de identidade for dado, então o qubit é preparado no estado máximo misturado.

Se o qubit estava inicialmente no estado $\ket$ {0} , esta operação prepara o qubit no estado de $+1$ de um determinado operador Pauli, ou, `PauliI` para, no estado maximamente misturado (ver <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Se o qubit estava num estado diferente de $\ket {0} $, esta operação aplica os seguintes portões: $H$ para `PauliX` , $HS$ para `PauliY` , $I$ para e para `PauliZ` <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="basis--pauli"></a>base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Um operador da Pauli $P$.


### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit para ser preparado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

