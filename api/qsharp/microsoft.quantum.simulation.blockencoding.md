---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Tipo definido pelo utilizador BlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 75fdbf13cf07d906982d4a611d1d25b3e29db2cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225436"
---
# <a name="blockencoding-user-defined-type"></a>Tipo definido pelo utilizador BlockEncoding

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um operador unitário onde um operador de interesse arbitrário é codificado no bloco superior esquerdo.

Ou seja, `BlockEncoding` é um $U$ unitário onde um operador arbitrário $H dólares de juros que atua no registo do sistema `s` é codificado no bloco superior esquerdo correspondente ao estado auxiliar $\ket {0} _a$. Isso é

$$ \start{align} (\bra {0} _a\otimes I_s)U(\ket {0} _a\otimes I_s) = H \end{align} $$.

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

