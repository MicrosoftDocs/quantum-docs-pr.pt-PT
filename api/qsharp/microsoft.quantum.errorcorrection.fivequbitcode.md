---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Função FiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853143"
---
# <a name="fivequbitcode-function"></a>Função FiveQubitCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um valor QECC que representa o codificador de código ⟦5, 1, 3⟧ com a medição da síndrome no local.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Saída : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Devolve uma implementação de um código de correção de erros quânticos especificando um `QECC` tipo.

## <a name="remarks"></a>Observações

Este código foi encontrado independentemente nos dois seguintes trabalhos:

- C. H. Bennett, D. DiVincenzo, J.A. Smolin e W.K. Wootters, "Emaranhado de estado misto e correção de erros quânticos", Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 e
- R. Laflamme, C. Miquel, J.P. Paz e W. H. Zurek, "Código perfeito de correção de erros quânticos", Phys. Rev. Lett. 77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019