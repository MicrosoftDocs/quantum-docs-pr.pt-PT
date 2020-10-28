---
uid: Microsoft.Quantum.Canon.RAll0
title: Operação RAll0
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715634"
---
# <a name="rall0-operation"></a>Operação RAll0

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Realiza uma operação de mudança de fase.

$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0\cdots 0}\bra{0\cdots 0}$.

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="phase--double"></a>fase : [Duplo](xref:microsoft.quantum.lang-ref.double)

A fase $\phi$ aplicada ao estado $\ket{0\cdots 0}\bra{0\cdots 0}cdots 0}$.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O registo cujo estado deve ser rodado por $R dólares.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.RAll1](xref:Microsoft.Quantum.Canon.RAll1)