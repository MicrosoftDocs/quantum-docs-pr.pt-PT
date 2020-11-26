---
uid: Microsoft.Quantum.Math.BitSizeI
title: Função BitSizeI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195856"
---
# <a name="bitsizei-function"></a>Função BitSizeI

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Para um número inteiro não `a` negativo, devolve o número de bits necessários para representar `a` .

Ou seja, devolve o menor $n$ de tal forma que $a < 2^n$.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a : [Int](xref:microsoft.quantum.lang-ref.int)

O inteiro cujo tamanho bit deve ser calculado.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O tamanho `a` de.