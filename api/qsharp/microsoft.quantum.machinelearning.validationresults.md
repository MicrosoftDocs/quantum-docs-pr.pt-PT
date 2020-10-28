---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidaçãoResults tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720430"
---
# <a name="validationresults-user-defined-type"></a>ValidaçãoResults tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Os resultados de ter validado um classificador contra um conjunto de amostras.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="nmisclassifications--int"></a>NMisclassificações : [Int](xref:microsoft.quantum.lang-ref.int)

O número de classificações erradas observadas durante a validação.
### <a name="nvalidationsamples--int"></a>NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)

