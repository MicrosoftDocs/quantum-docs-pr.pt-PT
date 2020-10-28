---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: Função SteaneCodeRecoveryFns
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712137"
---
# <a name="steanecoderecoveryfns-function"></a>Função SteaneCodeRecoveryFns

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Descodificador para partes combinadas de X e Z do grupo estabilizador do código quântico ⟦ 1, 1, 3⟧ Steane.

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>Saída :[(RecoveryFn,](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)[RecoveryFn)](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Tuple de funções do tipo `RecoveryFn` que faz uma medição de síndrome e `Result[]` devolve as `Pauli[]` operações que corrigem o erro detetado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)