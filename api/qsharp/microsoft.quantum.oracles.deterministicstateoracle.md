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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="ab84c-102">Tipo definido pelo utilizador DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="ab84c-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="ab84c-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ab84c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ab84c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab84c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab84c-105">Representa um oráculo para a preparação determinística do Estado.</span><span class="sxs-lookup"><span data-stu-id="ab84c-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="ab84c-106">A entrada para o oráculo $O$ é:</span><span class="sxs-lookup"><span data-stu-id="ab84c-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="ab84c-107">O registo que irá armazenar o estado quântico desejado $\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="ab84c-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="ab84c-108">Observações</span><span class="sxs-lookup"><span data-stu-id="ab84c-108">Remarks</span></span>

<span data-ttu-id="ab84c-109">Este oráculo definido por $O\ket {0} =\ket{\psi}$ atua na base computacional estado $\ket {0} $ para criar o estado $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="ab84c-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="ab84c-110">O primeiro parâmetro é o registo qubit de $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="ab84c-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>