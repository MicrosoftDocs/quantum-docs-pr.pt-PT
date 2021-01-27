---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operação EncodeIntoFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826327"
---
# <a name="encodeintofivequbitcode-operation"></a>Operação EncodeIntoFiveQubitCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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