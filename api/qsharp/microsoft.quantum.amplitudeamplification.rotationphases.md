---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotação Tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721770"
---
# <a name="rotationphases-user-defined-type"></a>Rotação Tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [](https://nuget.org/packages/)


Fases para uma sequência de rotações de um único qubit em amplificação de amplitude.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Observações

O primeiro parâmetro é um conjunto de fases para reflexões, expressas como um produto de rotações de um único qubit.
G.H. Baixo, I.L. https://arxiv.org/abs/1707.05391Chuang, ].