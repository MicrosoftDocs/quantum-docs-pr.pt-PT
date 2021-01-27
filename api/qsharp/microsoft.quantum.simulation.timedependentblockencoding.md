---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TempoDependentBlockEncoding tipo definido do utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: e2b191a4fc44f99c88f25da9b1ee6460d936740b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814268"
---
# <a name="timedependentblockencoding-user-defined-type"></a>TempoDependentBlockEncoding tipo definido do utilizador

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um `BlockEncoding` que é controlado por um registo de relógio.

Ou seja, `TimeDependentBlockEncoding` um $U$ unitário controlado por um estado $\ket{k}_d$ no registo do relógio `d` de modo a que um operador arbitrário $H_k$ de juros que atua no registo do sistema `s` esteja codificado no bloco superior esquerdo correspondente ao estado auxiliar $\ket {0} _a$. Isso é

$$ \start{align} (\bra {0} \_ a\otimes I_{ds})U(\ket {0} \_ a\otimes I_{ds}) = \sum_{k}\ket{k}}k} \_ d\otimes H_k.
\end{align} $$.

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

