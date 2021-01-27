---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotação Tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843971"
---
# <a name="rotationphases-user-defined-type"></a>Rotação Tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fases para uma sequência de rotações de um único qubit em amplificação de amplitude.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Observações

O primeiro parâmetro é um conjunto de fases para reflexões, expressas como um produto de rotações de um único qubit.
G.H. Baixo, I.L. https://arxiv.org/abs/1707.05391Chuang, ].