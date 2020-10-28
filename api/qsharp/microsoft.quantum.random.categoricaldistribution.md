---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: Função de distribuição categórica
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722820"
---
# <a name="categoricaldistribution-function"></a>Função de distribuição categórica

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [](https://nuget.org/packages/)


Devolve uma distribuição categórica discreta, na qual a probabilidade de cada uma das listas finitas de determinados resultados é explicitamente especificada.

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Entrada

### <a name="probs--double"></a>probs : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

As probabilidades de cada resultado a partir da distribuição categórica.
Estas probabilidades podem não ser normalizadas, mas devem ser todas não negativas.



## <a name="output--discretedistribution"></a>Saída : [Distribuição discreta](xref:Microsoft.Quantum.Random.DiscreteDistribution)

O índice `i` com `probs[i] / sum` probabilidade, onde está a soma `sum` dada por `probs` `Fold(PlusD, 0.0, probs)` .