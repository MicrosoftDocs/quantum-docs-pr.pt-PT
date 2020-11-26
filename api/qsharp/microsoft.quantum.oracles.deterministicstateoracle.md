---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definido pelo utilizador DeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193935"
---
# <a name="deterministicstateoracle-user-defined-type"></a>Tipo definido pelo utilizador DeterministicStateOracle

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um oráculo para a preparação determinística do Estado.

A entrada para o oráculo $O$ é:

- O registo que irá armazenar o estado quântico desejado $\ket{\psi} \_ s$.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observações

Este oráculo definido por $O\ket {0} =\ket{\psi}$ atua na base computacional estado $\ket {0} $ para criar o estado $\ket{\psi}$.
O primeiro parâmetro é o registo qubit de $\ket{\psi}$.