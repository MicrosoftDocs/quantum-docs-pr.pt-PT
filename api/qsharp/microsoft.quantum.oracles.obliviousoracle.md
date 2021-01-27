---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Tipo definido pelo utilizador Doósforo
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842553"
---
# <a name="obliviousoracle-user-defined-type"></a>Tipo definido pelo utilizador Doósforo

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um oráculo para amplificação de amplitude alheia.

As entradas para o oráculo $O$ são:

- O registo da Ancilla $a dólares em que $O$ atua.
- O registo do sistema $s$ em que é aplicado o $U$ unitário desejado, pós-seleccionado no registo $a$ estando no estado $\ket{t} \_ a$.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observações

Este oráculo definido por $$ O\ket{s} \_ a\ket{\psi} \_ s= \lambda\ket{t} \_ a U\ket{\psi} \_ s + \sqrt{1-|\lambda|^2}ket{t^\ket{\ket{t^\sqrt{1-|\lambda|^2}ket{t^\perp} \_ a\cdots $$ acts on the ancilla state $\ket{s} \_ a$ to implement the unitary $U$ on any system state $\ket{\psi} \_ s$ com amplitude $\lambda$ na base sinalizada por $\ket{t} \_ a$.
O primeiro parâmetro é o registo qubit de $\ket{s} \_ a$. O segundo parâmetro é o registo qubit de $\ket{\psi} \_ s$.