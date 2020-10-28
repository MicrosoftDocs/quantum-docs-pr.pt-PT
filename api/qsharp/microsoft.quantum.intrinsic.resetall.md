---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetTo operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711409"
---
# <a name="resetall-operation"></a>ResetTo operação

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [](https://nuget.org/packages/)


Dada uma série de qubits, meça-os e garanta que estão no estado de 0⟩ de modo a que possam ser libertados em segurança.

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Uma série de qubits cujos estados devem ser repostos para $\ket {0} $.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

