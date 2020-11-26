---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: função _UpdatedBias
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196706"
---
# <a name="_updatedbias-function"></a>função _UpdatedBias

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devolve um valor tendencioso que leva a uma pontuação de classificação quase mínima.

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="labeledprobabilities--doubleint"></a>rotulagemProbabilidades :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Int](xref:microsoft.quantum.lang-ref.int))[]




### <a name="bias--double"></a>parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

