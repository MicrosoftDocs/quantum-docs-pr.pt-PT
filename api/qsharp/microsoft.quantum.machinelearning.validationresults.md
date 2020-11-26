---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidaçãoResults tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211496"
---
# <a name="validationresults-user-defined-type"></a>ValidaçãoResults tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Os resultados de ter validado um classificador contra um conjunto de amostras.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="nmisclassifications--int"></a>NMisclassificações : [Int](xref:microsoft.quantum.lang-ref.int)

O número de classificações erradas observadas durante a validação.
### <a name="nvalidationsamples--int"></a>NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)

