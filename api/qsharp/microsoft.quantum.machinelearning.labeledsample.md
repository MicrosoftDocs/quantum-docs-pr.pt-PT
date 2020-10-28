---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido pelo utilizador LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711336"
---
# <a name="labeledsample-user-defined-type"></a>Tipo definido pelo utilizador LabeledSample

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Uma amostra, rotulada com uma classe à qual pertence essa amostra.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="features--double"></a>Características : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Um vetor de características para a amostra dada.
### <a name="label--int"></a>Etiqueta : [Int](xref:microsoft.quantum.lang-ref.int)

Um rótulo inteiro para a classe a que esta amostra pertence.