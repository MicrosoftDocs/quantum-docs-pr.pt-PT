---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Função InferredLabels
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196366"
---
# <a name="inferredlabels-function"></a>Função InferredLabels

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dada uma série de probabilidades de classificação e um enviesamento, devolve o rótulo inferido de cada probabilidade.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="bias--double"></a>parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)

O preconceito entre duas classes, normalmente o resultado do treino de um classificador.


### <a name="probabilities--double"></a>probabilidades : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma série de probabilidades de classificação para um conjunto de amostras, normalmente resultantes da estimativa de frequências de classificação.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

O rótulo deduzido de cada probabilidade de classificação.