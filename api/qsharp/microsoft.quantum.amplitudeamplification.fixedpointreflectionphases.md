---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Função FixedPointReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721857"
---
# <a name="fixedpointreflectionphases-function"></a>Função FixedPointReflectionPhases

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [](https://nuget.org/packages/)


Calcula as fases de reflexão parcial para amplificação da amplitude de ponto fixo.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Entrada

### <a name="nqueries--int"></a>nQueries : [Int](xref:microsoft.quantum.lang-ref.int)

Número de consultas ao oráculo de preparação do estado. Deve ser um número inteiro estranho.


### <a name="successmin--double"></a>successMin : [Duplo](xref:microsoft.quantum.lang-ref.double)

Probabilidade mínima de sucesso.



## <a name="output--reflectionphases"></a>Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Conjunto de fases que podem ser usadas na implementação do algoritmo quântico de amplificação de amplitude fixa.

## <a name="references"></a>Referências

Utilizamos as fases em "Amplificação de Amplitude de Ponto Fixo com um Número Ideal de Consultas"

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Consulte também "Metodologia de portões quânticos compostos"
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) para fases no `RotationPhases` formato.