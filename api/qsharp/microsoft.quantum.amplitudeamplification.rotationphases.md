---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotação Tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191368"
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