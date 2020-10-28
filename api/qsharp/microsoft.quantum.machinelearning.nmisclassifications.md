---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Função de classificações NMisclassificações
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709740"
---
# <a name="nmisclassifications-function"></a>Função de classificações NMisclassificações

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Tendo em conta um conjunto de rótulos inferidos e um conjunto de etiquetas corretas, o número de índices em que cada conjunto de rótulos difere.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Entrada

### <a name="proposed--int"></a>proposto : [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>real : [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de índices `idx` tal que `inferredLabels[idx] != actualLabels[idx]` . .