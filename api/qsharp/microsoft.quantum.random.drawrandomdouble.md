---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Operação DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847613"
---
# <a name="drawrandomdouble-operation"></a>Operação DrawRandomDouble

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Desenha um número real aleatório num determinado intervalo inclusivo.

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="min--double"></a>min : [Duplo](xref:microsoft.quantum.lang-ref.double)

O menor número real a ser desenhado.


### <a name="max--double"></a>max : [Duplo](xref:microsoft.quantum.lang-ref.double)

O maior número real a ser desenhado.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Um número real aleatório no intervalo inclusivo de `min` para `max` com probabilidade uniforme.

## <a name="example"></a>Exemplo

O seguinte corte Q# desenha aleatoriamente um ângulo entre $0$ e $2 \pi$:

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a>Observações

Falha se `max <= min` . .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)