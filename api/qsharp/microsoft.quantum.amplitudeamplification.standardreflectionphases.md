---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Função StandardReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721731"
---
# <a name="standardreflectionphases-function"></a>Função StandardReflectionPhases

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [](https://nuget.org/packages/)


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