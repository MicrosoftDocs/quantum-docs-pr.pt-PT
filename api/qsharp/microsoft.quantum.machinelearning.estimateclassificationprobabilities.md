---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operação De Classificação de Estimativas
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: eea503d042d6ffc241186c117a7c02ee72983b09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847725"
---
# <a name="estimateclassificationprobabilities-operation"></a>Operação De Classificação de Estimativas

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado um conjunto de amostras e um classificador sequencial, estima a probabilidade de classificação dessas amostras medindo repetidamente a saída do classificador em cada amostra.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

A tolerância para permitir a codificação da amostra numa operação de preparação do Estado.


### <a name="model--sequentialmodel"></a>modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

O modelo sequencial a utilizar para estimar as probabilidades de classificação das amostras dadas.


### <a name="samples--double"></a>amostras : [Duplo](xref:microsoft.quantum.lang-ref.double)[][]

Uma variedade de vetores de características para cada amostra ser classificada.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na estimativa da probabilidade de classificação.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma série de estimativas da probabilidade de classificação para cada amostra dada.