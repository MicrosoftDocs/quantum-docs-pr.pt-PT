---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Função FixedPointReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191453"
---
# <a name="fixedpointreflectionphases-function"></a>Função FixedPointReflectionPhases

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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