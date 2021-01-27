---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: Função SteaneCodeRecoveryFns
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 8dc715042f98b90b8cea7e2d6ecb5d02a78d297f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853033"
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