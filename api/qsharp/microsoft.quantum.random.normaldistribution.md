---
uid: Microsoft.Quantum.Random.NormalDistribution
title: Função NormalDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814176"
---
# <a name="normaldistribution-function"></a>Função NormalDistribution

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve uma distribuição normal com uma média e variação.

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrada

### <a name="mean--double"></a>média : [Duplo](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>variação : [Duplo](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>Exemplo

Os seguintes recolhem 10 amostras da distribuição normal com a média 2 e o desvio padrão 0.1:

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Random.StandardNormalDistribution](xref:Microsoft.Quantum.Random.StandardNormalDistribution)