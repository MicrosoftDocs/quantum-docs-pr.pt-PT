---
uid: Microsoft.Quantum.Math.PNorm
title: Função PNorm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722302"
---
# <a name="pnorm-function"></a>Função PNorm

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


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