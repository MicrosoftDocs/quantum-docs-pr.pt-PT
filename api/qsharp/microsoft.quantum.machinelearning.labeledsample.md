---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido pelo utilizador LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196332"
---
# <a name="labeledsample-user-defined-type"></a>Tipo definido pelo utilizador LabeledSample

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Uma amostra, rotulada com uma classe à qual pertence essa amostra.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="features--double"></a>Características : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Um vetor de características para a amostra dada.
### <a name="label--int"></a>Etiqueta : [Int](xref:microsoft.quantum.lang-ref.int)

Um rótulo inteiro para a classe a que esta amostra pertence.