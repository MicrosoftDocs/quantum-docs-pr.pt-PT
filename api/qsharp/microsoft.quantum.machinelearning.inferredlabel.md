---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Função InferredLabel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211785"
---
# <a name="inferredlabel-function"></a>Função InferredLabel

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dada a probabilidade de classificação e um enviesamento, devolve o rótulo inferido dessa probabilidade.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Entrada

### <a name="bias--double"></a>parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)

O preconceito entre duas classes, normalmente o resultado do treino de um classificador.


### <a name="probability--double"></a>probabilidade : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma probabilidade de classificação para uma determinada amostra, tipicamente resultante da estimativa da sua frequência de classificação.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O rótulo deduzido da dada probabilidade de classificação.