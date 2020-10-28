---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operação CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711535"
---
# <a name="ccnot-operation"></a>Operação CCNOT

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [](https://nuget.org/packages/)


Aplica o portão duplamente controlado -NÃO (CCNOT) a três qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="control1--qubit"></a>controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro qubit de controlo para o portão CCNOT.


### <a name="control2--qubit"></a>controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo qubit de controlo para o portão CCNOT.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de alvo para o portão CCNOT.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Equivalente a:

```qsharp
Controlled X([control1, control2], target);
```