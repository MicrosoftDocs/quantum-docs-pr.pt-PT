---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidaçãoResults tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846082"
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

