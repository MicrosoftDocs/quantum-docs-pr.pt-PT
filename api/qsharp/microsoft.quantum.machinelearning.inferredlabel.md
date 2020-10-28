---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: Função InferredLabel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722515"
---
# <a name="inferredlabel-function"></a>Função InferredLabel

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


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