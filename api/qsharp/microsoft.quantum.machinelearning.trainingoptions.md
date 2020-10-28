---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: FormaçãoOptions tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722375"
---
# <a name="trainingoptions-user-defined-type"></a>FormaçãoOptions tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Uma coleção de opções a serem usadas no treino de classificadores quânticos.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Itens nomeados

### <a name="learningrate--double"></a>LearningRate : [Duplo](xref:microsoft.quantum.lang-ref.double)

A taxa de aprendizagem através da qual os gradientes devem ser redimensionados ao atualizar os parâmetros do modelo durante as etapas de treino.
### <a name="tolerance--double"></a>Tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

A tolerância de aproximação a utilizar na preparação de amostras como estados quânticos.
### <a name="minibatchsize--int"></a>MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)

O número de amostras a utilizar em cada minibatch de treino.
### <a name="nmeasurements--int"></a>NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes para medir cada resultado de classificação para estimar a probabilidade de classificação.
### <a name="maxepochs--int"></a>MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)

O número máximo de épocas para treinar cada modelo.
### <a name="maxstalls--int"></a>MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)

O número máximo de vezes que uma época de treino é permitida para parar (aproximadamente zero gradiente) antes de falhar.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor : [Duplo](xref:microsoft.quantum.lang-ref.double)

A quantidade para redimensionar os modelos paralisados antes de voltar a tentar uma atualização.
### <a name="scoringperiod--int"></a>PontuaçãoPeriod : [Int](xref:microsoft.quantum.lang-ref.int)

O número de passos de gradiente a tomar entre pontos de pontuação.
Para obter a melhor precisão, desa um.
### <a name="verbosemessage--string---unit"></a>VerboseMessage : Unidade [de Cordas](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)

Uma função que pode ser usada para fornecer feedback verboso.

## <a name="remarks"></a>Observações

Este UDT não deve ser criado diretamente, mas deve ser especificado ligando e, em @"microsoft.quantum.machinelearning.defaulttrainingoptions" seguida, usando o `w/` operador para anular diferentes predefinições.

Por exemplo, utilizar 100.000 medições e, no máximo, 8 épocas de treino:

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Referências

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)