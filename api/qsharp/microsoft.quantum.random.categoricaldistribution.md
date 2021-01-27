---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: Função de distribuição categórica
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842355"
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

## <a name="example"></a>Exemplo

O seguinte código Q# mostrará 0 com probabilidade 30% e 1 com probabilidade de 70%:

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```