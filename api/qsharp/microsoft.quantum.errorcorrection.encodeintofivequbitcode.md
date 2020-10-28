---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operação EncodeIntoFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712400"
---
# <a name="encodeintofivequbitcode-operation"></a>Operação EncodeIntoFiveQubitCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Codifica o código quântico ⟦5, 1, 3⟧.

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrada

### <a name="physregister--qubit"></a>physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um qubit que representa um estado não codificado. Esta matriz `Qubit[]` é de comprimento 1.


### <a name="auxqubits--qubit"></a>auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits auxiliares que serão utilizados para representar o estado codificado.



## <a name="output--logicalregister"></a>Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Uma variedade de qubits físicos do tipo `LogicalRegister` que armazenam o estado codificado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)