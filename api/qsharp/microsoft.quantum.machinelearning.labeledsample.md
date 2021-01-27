---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido pelo utilizador LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846968"
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