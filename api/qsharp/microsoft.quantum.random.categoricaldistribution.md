---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: Função de distribuição categórica
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210255"
---
# <a name="categoricaldistribution-function"></a>Função de distribuição categórica

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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