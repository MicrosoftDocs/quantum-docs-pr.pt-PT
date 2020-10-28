---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definido pelo utilizador DeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724293"
---
# <a name="deterministicstateoracle-user-defined-type"></a>Tipo definido pelo utilizador DeterministicStateOracle

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [](https://nuget.org/packages/)


Representa um oráculo para a preparação determinística do Estado.

A entrada para o oráculo $O$ é:

- O registo que irá armazenar o estado quântico desejado $\ket{\psi} \_ s$.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observações

Este oráculo definido por $O\ket {0} =\ket{\psi}$ atua na base computacional estado $\ket {0} $ para criar o estado $\ket{\psi}$.
O primeiro parâmetro é o registo qubit de $\ket{\psi}$.