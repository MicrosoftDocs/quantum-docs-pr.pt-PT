---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: Função de distribuição contínua UniformDis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709432"
---
# <a name="continuousuniformdistribution-function"></a>Função de distribuição contínua UniformDis

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Observações

Falha se `max <= min` . .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)