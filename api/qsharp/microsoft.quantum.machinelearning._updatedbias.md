---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: função _UpdatedBias
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 41a51d8a6a8af299ce3e84b727336b098a3d1160
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844433"
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

