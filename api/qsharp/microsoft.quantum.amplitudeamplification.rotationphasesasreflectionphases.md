---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Função Velocidadess De RotaçãoAsReflectionAs
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191198"
---
# <a name="rotationphasesasreflectionphases-function"></a>Função Velocidadess De RotaçãoAsReflectionAs

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte fases especificadas como rotações de um único qubit para fases especificadas como reflexos parciais.

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrada

### <a name="rotphases--rotationphases"></a>rotfases : [Velocidades de rotação](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

Matriz de rotações de um único qubit a converter em reflexos parciais.



## <a name="output--reflectionphases"></a>Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Uma operação que implementa fases especificadas como reflexos parciais.

## <a name="references"></a>Referências

Usamos a convenção em

- [ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) por relacionar fases de rotação de um único qubit às fases do operador de reflexão.