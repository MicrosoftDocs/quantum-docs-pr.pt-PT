---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Preparar operação Do Estado dePauliEigen
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193697"
---
# <a name="preparepaulieigenstate-operation"></a>Preparar operação Do Estado dePauliEigen

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara um qubit no eigenstate positivo de um determinado operador Pauli.
Se o operador de identidade for dado, então o qubit é preparado no estado máximo misturado.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Description

Se o qubit estava inicialmente no estado $\ket$ {0} , esta operação prepara o qubit no estado de $+1$ de um determinado operador Pauli, ou, `PauliI` para, no estado maximamente misturado (ver <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Se o qubit estava num estado diferente de $\ket {0} $, esta operação aplica os seguintes portões: $H$ para `PauliX` , $HS$ para `PauliY` , $I$ para e para `PauliZ` <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .

## <a name="input"></a>Entrada

### <a name="basis--pauli"></a>base : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Um operador da Pauli $P$.


### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit para ser preparado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

