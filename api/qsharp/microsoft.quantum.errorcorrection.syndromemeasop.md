---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido pelo utilizador SyndromeMeasOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200259"
---
# <a name="syndromemeasop-user-defined-type"></a>Tipo definido pelo utilizador SyndromeMeasOp

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma operação que é usada para medir a síndrome de um bloco de código que corrige erros.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Observações

A assinatura `(LogicalRegister => Syndrome)` representa uma operação que atua conjuntamente nos qubits `LogicalRegister` e alguns qubits auxiliares seguidos de uma medição dos qubits auxiliares para extrair um `Syndrome` valor que representa as `Result[]` destas medições.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft.Quantum.ErrorCorrection.Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)