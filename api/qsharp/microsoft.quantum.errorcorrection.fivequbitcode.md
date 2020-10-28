---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Função FiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712344"
---
# <a name="fivequbitcode-function"></a>Função FiveQubitCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


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