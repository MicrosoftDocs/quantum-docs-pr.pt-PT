---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Operação EncodeIntoSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826194"
---
# <a name="encodeintosteanecode-operation"></a>Operação EncodeIntoSteaneCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Uma operação de codificação que mapeia um registo quântico não codificado para um registo quântico codificado sob o código quântico de 1, 3 ⟧ ⟦.

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrada

### <a name="physregister--qubit"></a>physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo qubit que detém um estado quântico não codificado


### <a name="auxqubits--qubit"></a>auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo qubit que é inicialmente zero e que é adicionado ao sistema quântico para que uma operação de codificação possa ser realizada



## <a name="output--logicalregister"></a>Saída : [Registo Lógico](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Um registo quântico que mantém o estado após a aplicação do codificar Steane

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)