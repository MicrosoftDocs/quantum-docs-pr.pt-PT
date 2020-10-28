---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: Função InferredLabels
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722484"
---
# <a name="inferredlabels-function"></a>Função InferredLabels

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


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