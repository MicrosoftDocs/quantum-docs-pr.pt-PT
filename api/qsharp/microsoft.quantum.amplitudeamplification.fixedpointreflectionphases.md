---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Função FixedPointReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845846"
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