---
uid: Microsoft.Quantum.Math.PNorm
title: Função PNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847656"
---
# <a name="pnorm-function"></a>Função PNorm

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a `L(p)` norma de um vetor de `Double` s.

Ou seja, dado um conjunto $x$ de tipo `Double[]` , isto devolve o $p$-norm $ x \| \| \_ p= (\sum_{j}|x_j|^{p})^{1/p}$.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Entrada

### <a name="p--double"></a>p : [Duplo](xref:microsoft.quantum.lang-ref.double)

O expoente $p$ na norma de $p dólares.


### <a name="array--double"></a>matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

O $p $-norm $ \| x \| _p$.