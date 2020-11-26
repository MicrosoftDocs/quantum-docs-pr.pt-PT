---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Função amostrada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211632"
---
# <a name="sampled-function"></a>Função amostrada

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

