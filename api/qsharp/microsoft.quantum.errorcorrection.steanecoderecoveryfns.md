---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: Função SteaneCodeRecoveryFns
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 7395996e75c5a1c0c5d13f76d9ec76acae5683c7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200412"
---
# <a name="steanecoderecoveryfns-function"></a>Função SteaneCodeRecoveryFns

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Descodificador para partes combinadas de X e Z do grupo estabilizador do código quântico ⟦ 1, 1, 3⟧ Steane.

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>Saída :[(RecoveryFn,](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)[RecoveryFn)](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Tuple de funções do tipo `RecoveryFn` que faz uma medição de síndrome e `Result[]` devolve as `Pauli[]` operações que corrigem o erro detetado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)