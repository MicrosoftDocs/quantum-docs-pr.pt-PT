---
uid: Microsoft.Quantum.Math.PNorm
title: Função PNorm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194734"
---
# <a name="pnorm-function"></a>Função PNorm

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a `L(p)` norma de um vetor de `Double` s.

Ou seja, dado um conjunto $x$ de `Double[]` tipo, isto devolve o $p$-norm $ \| x \| \_ p= (\sum_{j}[x_j^{p})^{1/p}$.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Entrada

### <a name="p--double"></a>p : [Duplo](xref:microsoft.quantum.lang-ref.double)

O expoente $p$ na norma de $p dólares.


### <a name="array--double"></a>matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

O $p $-norm $ \| x \| _p$.