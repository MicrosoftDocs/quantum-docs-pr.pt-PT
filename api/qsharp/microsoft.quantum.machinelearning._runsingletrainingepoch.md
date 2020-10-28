---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: operação _RunSingleTrainingEpoch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720634"
---
# <a name="_runsingletrainingepoch-operation"></a>operação _RunSingleTrainingEpoch

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Realizar uma época de treino de classificador sequencial num subconjunto de amostras de dados.

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Entrada

### <a name="encodedsamples--labeledsamplestategenerator"></a>quartos codificados :[(LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]




### <a name="schedule--samplingschedule"></a>calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore : [Int](xref:microsoft.quantum.lang-ref.int)

O número de passos de gradiente a tomar entre pontos de pontuação.
Para obter a melhor precisão, desa um.


### <a name="options--trainingoptions"></a>opções : [Opções de Formação](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Opções a serem usadas no treino.


### <a name="model--sequentialmodel"></a>modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

O modelo sequencial a ser treinado.


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)

O melhor número de classificações erradas observadas em épocas anteriores.



## <a name="output--intsequentialmodel"></a>Saída : ([Int,](xref:microsoft.quantum.lang-ref.int)[SequencialModel)](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

- O menor número de desclassificações observadas nesta época.
- O novo melhor modelo sequencial encontrado.