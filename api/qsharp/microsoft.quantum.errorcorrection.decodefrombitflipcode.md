---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Descodificar operaçãoFromBitFlipCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712484"
---
# <a name="decodefrombitflipcode-operation"></a>Descodificar operaçãoFromBitFlipCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Descodifica do código bit-flip [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip.

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrada

### <a name="logicalregister--logicalregister"></a>LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Um bloco de código do código bit-flip.



## <a name="output--qubitqubit"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Um tuple dos dados codificados no registo lógico, e os qubits auxiliares usados para representar a síndrome.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)