---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: Função BitFlipRecoveryFn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712498"
---
# <a name="bitfliprecoveryfn-function"></a>Função BitFlipRecoveryFn

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Função para recuperação As operações de Pauli para a medição dada da síndrome por procura de tabela para o código de viragem ⟦3, 1, 1⟧ bit flip.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Saída : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Função do tipo `RecoveryFn` que faz uma medição da síndrome e `Result[]` devolve as `Pauli[]` operações que corrigem o erro detetado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)