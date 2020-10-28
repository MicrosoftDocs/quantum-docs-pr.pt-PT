---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Função amostrada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722428"
---
# <a name="sampled-function"></a>Função amostrada

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Amostras de uma determinada matriz, usando o horário dado.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="schedule--samplingschedule"></a>calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Um horário a utilizar em valores de amostragem.


### <a name="values--t"></a>valores : 'T[]

Uma variedade de valores a serem amostrados.



## <a name="output--t"></a>Saída : 'T].

Uma série de elementos de valores, seguindo o horário dado.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

