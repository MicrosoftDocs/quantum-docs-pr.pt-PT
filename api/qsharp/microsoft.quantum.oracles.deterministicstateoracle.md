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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="73c0f-102">Tipo definido pelo utilizador DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="73c0f-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="73c0f-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="73c0f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="73c0f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73c0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73c0f-105">Representa um oráculo para a preparação determinística do Estado.</span><span class="sxs-lookup"><span data-stu-id="73c0f-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="73c0f-106">A entrada para o oráculo $O$ é:</span><span class="sxs-lookup"><span data-stu-id="73c0f-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="73c0f-107">O registo que irá armazenar o estado quântico desejado $\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="73c0f-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="73c0f-108">Observações</span><span class="sxs-lookup"><span data-stu-id="73c0f-108">Remarks</span></span>

<span data-ttu-id="73c0f-109">Este oráculo definido por $O\ket {0} =\ket{\psi}$ atua na base computacional estado $\ket {0} $ para criar o estado $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="73c0f-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="73c0f-110">O primeiro parâmetro é o registo qubit de $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="73c0f-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>