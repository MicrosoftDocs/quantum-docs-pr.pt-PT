---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Função de distribuição contínua UniformDis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842325"
---
# <a name="continuousuniformdistribution-function"></a>Função de distribuição contínua UniformDis

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve uma distribuição uniforme sobre um determinado intervalo inclusivo.

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrada

### <a name="min--double"></a>min : [Duplo](xref:microsoft.quantum.lang-ref.double)

O menor número real a ser desenhado.


### <a name="max--double"></a>max : [Duplo](xref:microsoft.quantum.lang-ref.double)

O maior número real a ser desenhado.



## <a name="output--continuousdistribution"></a>Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Uma distribuição cujas variações aleatórias são números reais no intervalo inclusivo de `min` para `max` com probabilidade uniforme.

## <a name="example"></a>Exemplo

O seguinte corte Q# desenha aleatoriamente um ângulo entre $0$ e $2 \pi$:

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>Observações

Falha se `max <= min` . .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)