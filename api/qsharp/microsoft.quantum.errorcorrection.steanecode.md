---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: Função SteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712179"
---
# <a name="steanecode-function"></a>Função SteaneCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Devolve um valor CSS que representa o codificador de código Steane ⟦7, 1, 3⟧ com a medição da síndrome in-place.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Saída : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Um objeto do tipo CSS que recolhe todos os dados relevantes para executar a codificação e correção de erros para o código Steane ⟦7, 1, 3⟧.

## <a name="remarks"></a>Observações

Este código foi encontrado no seguinte papel:

- A. Steane, "Múltipla interferência de partículas e correção de erros quânticos", Proc. Roy, o que estás a fazer Soc. Lond. A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.