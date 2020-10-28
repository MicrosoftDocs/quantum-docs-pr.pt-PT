---
uid: Microsoft.Quantum.Math.PNormalized
title: Função PNormalizada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722288"
---
# <a name="pnormalized-function"></a>Função PNormalizada

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Normaliza um vetor de `Double` s na `L(p)` norma.

Isto é, dado um conjunto $x$ de `Double[]` tipo, este retorna um conjunto onde todos os elementos são divididos pela norma de $p$ \| x \| _p$.

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Entrada

### <a name="p--double"></a>p : [Duplo](xref:microsoft.quantum.lang-ref.double)

O expoente $p$ na norma de $p dólares.


### <a name="array--double"></a>matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

A matriz $x$ normalizada pela norma de $p$-norm $ \| x \| _p$.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Math.PNorm](xref:Microsoft.Quantum.Math.PNorm)