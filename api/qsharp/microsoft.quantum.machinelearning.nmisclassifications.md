---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Função de classificações NMisclassificações
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196315"
---
# <a name="nmisclassifications-function"></a>Função de classificações NMisclassificações

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Tendo em conta um conjunto de rótulos inferidos e um conjunto de etiquetas corretas, o número de índices em que cada conjunto de rótulos difere.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Entrada

### <a name="proposed--int"></a>proposto : [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>real : [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de índices `idx` tal que `inferredLabels[idx] != actualLabels[idx]` . .