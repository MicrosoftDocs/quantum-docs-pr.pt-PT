---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Operação EncodeIntoBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712403"
---
# <a name="encodeintobitflipcode-operation"></a>Operação EncodeIntoBitFlipCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


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