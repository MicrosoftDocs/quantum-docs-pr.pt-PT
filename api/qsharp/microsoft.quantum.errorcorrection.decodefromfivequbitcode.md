---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Descodificar OperaçãoFromFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712470"
---
# <a name="decodefromfivequbitcode-operation"></a>Descodificar OperaçãoFromFiveQubitCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Descodifica o código quântico ⟦5, 1, 3⟧.

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrada

### <a name="logicalregister--logicalregister"></a>LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Uma série de qubits que representam o estado lógico codificado do código 5-qubit.



## <a name="output--qubitqubit"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Uma matriz qubit de comprimento 1 representando o estado não codificado no primeiro parâmetro, juntamente com qubits auxiliares no segundo parâmetro.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)