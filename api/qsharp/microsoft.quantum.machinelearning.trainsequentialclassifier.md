---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operação TrainSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711308"
---
# <a name="trainsequentialclassifier-operation"></a>Operação TrainSequentialClassifier

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Dada a estrutura de um classificador sequencial, treina o classificador num determinado conjunto de treino rotulado.

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Entrada

### <a name="models--sequentialmodel"></a>modelos : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]

Uma série de modelos a utilizar como pontos de partida durante o treino.


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

- [Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)