---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Função StandardReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843922"
---
# <a name="standardreflectionphases-function"></a>Função StandardReflectionPhases

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula as fases de reflexão parcial para amplificação de amplitude padrão.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrada

### <a name="niterations--int"></a>niterações : [Int](xref:microsoft.quantum.lang-ref.int)

Número de iterações de amplificação de amplitude para gerar fases de reflexão parcial para.



## <a name="output--reflectionphases"></a>Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Uma operação que implementa fases especificadas como reflexões parciais

## <a name="remarks"></a>Observações

Todas as fases são $\pi$, exceto para o primeiro reflexo sobre o estado de início e a última reflexão sobre o estado alvo, que são $0$.