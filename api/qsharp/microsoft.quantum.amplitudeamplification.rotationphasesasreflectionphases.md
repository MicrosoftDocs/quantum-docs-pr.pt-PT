---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Função Velocidadess De RotaçãoAsReflectionAs
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843941"
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