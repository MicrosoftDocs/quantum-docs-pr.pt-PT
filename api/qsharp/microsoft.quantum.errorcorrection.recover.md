---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Operação de recuperação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712207"
---
# <a name="recover-operation"></a>Operação de recuperação

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Executa uma única ronda de correção de erros por um código quântico descrito por um `QECC` tipo.

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Entrada

### <a name="code--qecc"></a>código : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Um código de correção de erros quânticos embalado como um `QECC` tipo descreve a codificação e descodificação dos dados quânticos e como as síndromes de erro devem ser medidas.


### <a name="fn--recoveryfn"></a>fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

A `RecoveryFn` que mapeia cada síndrome de erro para as `Pauli[]` operações que corrigem o erro detetado.


### <a name="logicalregister--logicalregister"></a>LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Uma matriz de qubits onde o código estabilizador é definido.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [Microsoft.Quantum.ErrorCorrection.RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)