---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: Função de distribuição DiscreteUniformD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720298"
---
# <a name="discreteuniformdistribution-function"></a>Função de distribuição DiscreteUniformD

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [](https://nuget.org/packages/)


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