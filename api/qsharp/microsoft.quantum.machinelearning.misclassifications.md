---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Função de classificações erradas
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211683"
---
# <a name="misclassifications-function"></a>Função de classificações erradas

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado um conjunto de etiquetas inferidas e um conjunto de etiquetas corretas, os índices de reposição para o local onde cada conjunto de rótulos difere.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="inferredlabels--int"></a>inferiuLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]

As etiquetas inferidas para um determinado conjunto de formação ou validação.


### <a name="actuallabels--int"></a>realLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]

Os verdadeiros rótulos para um determinado conjunto de treino ou validação.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma série de índices `idx` tal `inferredLabels[idx] != actualLabels[idx]` que.