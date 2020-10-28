---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operação PermuteQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715662"
---
# <a name="permutequbits-operation"></a>Operação PermuteQubits

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Permutes qubits utilizando a operação SWAP.

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="ordering--int"></a>ordenação : [Int](xref:microsoft.quantum.lang-ref.int)[]

Descreve a nova encomenda dos qubits, onde o qubit no índice i estará agora a encomendar[i].


### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo qubit para ser agido.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

