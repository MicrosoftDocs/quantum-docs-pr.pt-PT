---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: Função DeTrainingOptions padrão
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856000"
---
# <a name="defaulttrainingoptions-function"></a>Função DeTrainingOptions padrão

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devolve um conjunto predefinido de opções para classificadores de treino.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Saída : [Opções de Formação](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Um conjunto razoável de opções de treino predefinidos para utilização quando os classificadores de treino.

## <a name="example"></a>Exemplo

Para utilizar as opções predefinidos, mas com medições adicionais, utilize o `w/` operador:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```