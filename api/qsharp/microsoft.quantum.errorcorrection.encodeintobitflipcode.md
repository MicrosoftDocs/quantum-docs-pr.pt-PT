---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operação EncodeIntoBitFlipCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 44034a864c946a7d3dbb21bad5ee500660709f1a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826685"
---
# <a name="encodeintobitflipcode-operation"></a>Operação EncodeIntoBitFlipCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica o código bit-flip [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip.

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrada

### <a name="physregister--qubit"></a>physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits físicos que representam os dados a proteger.


### <a name="auxqubits--qubit"></a>auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits auxiliares inicialmente no estado $\ket {00} $ a ser usado na codificação dos dados a proteger.



## <a name="output--logicalregister"></a>Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Os qubits físicos e auxiliares utilizados na codificação, representados como um registo lógico.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)