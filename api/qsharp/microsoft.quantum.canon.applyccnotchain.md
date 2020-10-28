---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: AplicaÇÃO Operação CCTChain
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718390"
---
# <a name="applyccnotchain-operation"></a>AplicaÇÃO Operação CCTChain

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Implementa uma cascata de portões CCNOT controlados em bits correspondentes de dois registos qubit, atuando no próximo qubit de um dos registos.
Partindo dos qubits na posição 0 em ambos os registos como controlos, o CCNOT é aplicado ao qubit na posição 1 do registo-alvo, sendo depois controlado pelos qubits na posição 1, atuando no qubit na posição 2 do registo-alvo, etc., terminando com uma ação sobre o qubit alvo na posição `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo qubit, apenas utilizado para controlos.


### <a name="targets--qubit"></a>alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo qubit, usado para controlos e como alvo.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

O registo de qubits-alvo deve ter um qubit mais do que o outro registo.