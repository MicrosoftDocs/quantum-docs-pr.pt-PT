---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Tipo definido pelo utilizador Doósforo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710989"
---
# <a name="obliviousoracle-user-defined-type"></a>Tipo definido pelo utilizador Doósforo

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [](https://nuget.org/packages/)


Representa um oráculo para amplificação de amplitude alheia.

As entradas para o oráculo $O$ são:

- O registo da Ancilla $a dólares em que $O$ atua.
- O registo do sistema $s$ em que é aplicado o $U$ unitário desejado, pós-seleccionado no registo $a$ estando no estado $\ket{t} \_ a$.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observações

Este oráculo definido por $$ O\ket{s} \_ a\ket{\psi} \_ s= \lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-\lambda/^2}ket{t^\perp} \_ a\cdots $$ atua no estado de ancilla $\ket{s} \_ a$ para implementar o $U$ unitário em qualquer estado do sistema $\ket{\psi} \_ s$ com amplitude $\lambda$ na base sinalizada por $\ket{t} \_ a$.
O primeiro parâmetro é o registo qubit de $\ket{s} \_ a$. O segundo parâmetro é o registo qubit de $\ket{\psi} \_ s$.