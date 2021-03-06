---
uid: Microsoft.Quantum.Oracles.StateOracle
title: EstadoOracle tipo definido do utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854473"
---
# <a name="stateoracle-user-defined-type"></a>EstadoOracle tipo definido do utilizador

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um oráculo para a preparação do estado.

As entradas para o oráculo $O$ são:

- Um inteiro a indexar o qubit da bandeira $f$.
- O registo do sistema $s$ que armazenará o estado quântico desejado $\ket{\psi} \_ s$.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observações

Este oráculo definido por $$ O\ket {0} \_ {f}\ket {0} \_ s= \lambda\ket {1} \_ f\ket f\ket{\psi} \_ s + \sqrt{1-|\lambda|^2}ket {0} \_ f\cdots, $$ acts on the computational basis state $\ket {0} \_ {f}\ket {0} \_ s$ para criar o estado-alvo $\ket{\psi} \_ s$ com amplitude $\lambda$ na base assinalada por $\ket {1} \_ f$.
O primeiro parâmetro é um índice para o registo qubit de $\ket {0} \_ f$. O segundo parâmetro abrangeu ambos os registos.