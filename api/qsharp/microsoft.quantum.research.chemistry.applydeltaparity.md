---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Aplicação Operação Vídeopardade
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851099"
---
# <a name="applydeltaparity-operation"></a>Aplicação Operação Vídeopardade

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Computa a diferença de paridade entre um PQRS anterior... termos e o próximo PQRS... termo. Esta diferença é calculada num qubit auxiliar.

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="prevfermionicterm--int"></a>prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]

Lista de índices para PQRS anteriores... termos.


### <a name="nextfermionicterm--int"></a>nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]

Lista de índices para o próximo PQRS... termos.


### <a name="aux--qubit"></a>aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliar sobre os resultados do cálculo da paridade são armazenados.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit agido por todos os PQRS... termos.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Isto pressupõe que os índices de P < Q < R < S < ... tanto para o prevPQ como para o próximoPQ.