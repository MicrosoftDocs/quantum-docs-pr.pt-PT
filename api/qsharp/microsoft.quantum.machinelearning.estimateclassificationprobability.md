---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operação de Qualificação de Estimativas
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709771"
---
# <a name="estimateclassificationprobability-operation"></a>Operação de Qualificação de Estimativas

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Dada uma amostra e um classificador sequencial, estima a probabilidade de classificação dessa amostra medindo repetidamente a saída do classificador na amostra dada.

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

A tolerância para permitir a codificação da amostra numa operação de preparação do Estado.


### <a name="model--sequentialmodel"></a>modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

O modelo sequencial a utilizar para estimar a probabilidade de classificação para a amostra dada.


### <a name="sample--double"></a>amostra : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

O vetor de recurso para a amostra ser classificado.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na estimativa da probabilidade de classificação.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma estimativa da probabilidade de classificação para a amostra dada.