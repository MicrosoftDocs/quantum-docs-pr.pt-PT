---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: Operação TrainSequentialClassifierAtModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 02a300a2e1029d0e09aba19d090e15128fede717
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211473"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>Operação TrainSequentialClassifierAtModel

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dada a estrutura de um classificador sequencial, treina o classificador num determinado conjunto de formação rotulado, a partir de um determinado modelo.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Entrada

### <a name="model--sequentialmodel"></a>modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

O modelo sequencial a ser utilizado como ponto de partida para o treino.


### <a name="samples--labeledsample"></a>amostras : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Um conjunto de dados de formação rotulados que serão utilizados para realizar treinos.


### <a name="options--trainingoptions"></a>opções : [Opções de Formação](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Configuração a utilizar durante o treino; ver @"microsoft.quantum.machinelearning.trainingoptions" e para mais @"microsoft.quantum.machinelearning.defaulttrainingoptions" detalhes.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Um calendário de amostragem a utilizar ao selecionar amostras dos dados de treino durante as etapas de treino.


### <a name="validationschedule--samplingschedule"></a>validaçãoSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Um calendário de amostragem a utilizar ao selecionar amostras dos dados de treino ao selecionar qual ponto de partida resultou na melhor pontuação do classificador.



## <a name="output--sequentialmodelint"></a>Saída : ([SequencialModel,](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[Int)](xref:microsoft.quantum.lang-ref.int)

- Uma parametrização do classificador dado e um enviesamento entre as duas classes, correspondente ao melhor resultado de cada um dos pontos de partida dados.
- O número de falhas observadas no melhor modelo de classificador.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.MachineLearning.TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)