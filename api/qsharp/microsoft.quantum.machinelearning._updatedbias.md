---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: função _UpdatedBias
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 2704d08e4c1ce868e1fd9065c3cab0285d431094
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720563"
---
# <a name="_updatedbias-function"></a>função _UpdatedBias

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Devolve um valor tendencioso que leva a uma pontuação de classificação quase mínima.

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="labeledprobabilities--doubleint"></a>rotulagemProbabilidades :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Int](xref:microsoft.quantum.lang-ref.int))[]




### <a name="bias--double"></a>parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

