---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Validar operação DesequentialClassifier
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 5174085edbfd846e8f6649f33e325fd1979ae6a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196111"
---
# <a name="validatesequentialclassifier-operation"></a>Validar operação DesequentialClassifier

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Valida um determinado classificador sequencial contra um determinado conjunto de amostras pré-etiquetadas.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Entrada

### <a name="model--sequentialmodel"></a>modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

O modelo sequencial a ser validado.


### <a name="samples--labeledsample"></a>amostras : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

As amostras a utilizar para validar o modelo dado.


### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

A tolerância de aproximação a utilizar na codificação de cada amostra como entrada para o classificador sequencial.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na classificação de cada amostra.


### <a name="validationschedule--samplingschedule"></a>validaçãoSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

O calendário através do qual as amostras devem ser retiradas do conjunto de validação.



## <a name="output--validationresults"></a>Saída : [ValidaçõesResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

Os resultados da validação dada.