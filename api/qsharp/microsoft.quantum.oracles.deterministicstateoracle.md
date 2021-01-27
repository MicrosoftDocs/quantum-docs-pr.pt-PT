---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definido pelo utilizador DeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842581"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="d53d1-102">Tipo definido pelo utilizador DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="d53d1-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="d53d1-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d53d1-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d53d1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d53d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d53d1-105">Representa um oráculo para a preparação determinística do Estado.</span><span class="sxs-lookup"><span data-stu-id="d53d1-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="d53d1-106">A entrada para o oráculo $O$ é:</span><span class="sxs-lookup"><span data-stu-id="d53d1-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="d53d1-107">O registo que irá armazenar o estado quântico desejado $\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="d53d1-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="d53d1-108">Observações</span><span class="sxs-lookup"><span data-stu-id="d53d1-108">Remarks</span></span>

<span data-ttu-id="d53d1-109">Este oráculo definido por $O\ket {0} =\ket{\psi}$ atua na base computacional estado $\ket {0} $ para criar o estado $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="d53d1-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="d53d1-110">O primeiro parâmetro é o registo qubit de $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="d53d1-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>