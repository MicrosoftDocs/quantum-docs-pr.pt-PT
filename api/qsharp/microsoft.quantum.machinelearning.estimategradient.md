---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operação EstimativaGradient
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211853"
---
# <a name="estimategradient-operation"></a>Operação EstimativaGradient

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Estima o gradiente de formação para um classificador sequencial num determinado modelo e para uma determinada entrada codificada.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Entrada

### <a name="model--sequentialmodel"></a>modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

O modelo sequencial cujo gradiente deve ser estimado.


### <a name="encodedinput--stategenerator"></a>incodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Uma entrada para o classificador sequencial, codificada numa operação de preparação do estado.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na estimativa do gradiente.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma estimativa do gradiente de formação nos parâmetros de entrada e modelo dados.

## <a name="remarks"></a>Observações

Esta operação utiliza um teste Hadamard e a técnica de mudança de parâmetros em conjunto para estimar o gradiente.