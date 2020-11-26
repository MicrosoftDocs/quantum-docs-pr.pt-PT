---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operação DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193000"
---
# <a name="drawcategorical-operation"></a>Operação DrawCategorical

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Extrai uma amostra aleatória de uma distribuição categórica especificada por uma lista de probablidades.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Description

A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice.
Elementos de matriz que são iguais a zero são ignorados e os seus índices nunca são devolvidos. Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for maior que zero, então a operação falha.

## <a name="input"></a>Entrada

### <a name="probs--double"></a>probs : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma matriz de números de pontos flutuantes proporcional à probabilidade de selecionar cada índice.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro $i$ com probabilidade $\Pr(i) = p_i / \sum_i p_i$, onde $p_i$ é o elemento $i$th de `probs` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Random.CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)