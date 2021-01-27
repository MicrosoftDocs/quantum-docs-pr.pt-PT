---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Operação DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851144"
---
# <a name="drawrandomint-operation"></a>Operação DrawRandomInt

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Desenha um inteiro aleatório numa determinada gama inclusiva.

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="min--int"></a>min : [Int](xref:microsoft.quantum.lang-ref.int)

O menor número inteiro a ser desenhado.


### <a name="max--int"></a>max : [Int](xref:microsoft.quantum.lang-ref.int)

O maior inteiro a ser desenhado.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro na gama inclusiva de `min` até `max` com probabilidade uniforme.

## <a name="example"></a>Exemplo

O seguinte corte Q# rola aleatoriamente um die de seis lados:

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a>Observações

Falha se `max <= min` . .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)