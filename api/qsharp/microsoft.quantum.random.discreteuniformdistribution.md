---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Função de distribuição DiscreteUniformD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193017"
---
# <a name="discreteuniformdistribution-function"></a>Função de distribuição DiscreteUniformD

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve uma distribuição uniforme sobre uma determinada gama inclusiva.

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>Entrada

### <a name="min--int"></a>min : [Int](xref:microsoft.quantum.lang-ref.int)

O menor número inteiro a ser desenhado.


### <a name="max--int"></a>max : [Int](xref:microsoft.quantum.lang-ref.int)

O maior inteiro a ser desenhado.



## <a name="output--discretedistribution"></a>Saída : [Distribuição discreta](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Uma distribuição cujas variações aleatórias são inteiros na gama inclusiva de `min` até `max` com probabilidade uniforme.

## <a name="remarks"></a>Observações

Falha se `max <= min` . .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)