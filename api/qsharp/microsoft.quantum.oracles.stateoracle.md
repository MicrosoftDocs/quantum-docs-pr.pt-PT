---
uid: Microsoft.Quantum.Oracles.StateOracle
title: EstadoOracle tipo definido do utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724223"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="5f937-102">EstadoOracle tipo definido do utilizador</span><span class="sxs-lookup"><span data-stu-id="5f937-102">StateOracle user defined type</span></span>

<span data-ttu-id="5f937-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5f937-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5f937-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f937-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f937-105">Representa um oráculo para a preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="5f937-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="5f937-106">As entradas para o oráculo $O$ são:</span><span class="sxs-lookup"><span data-stu-id="5f937-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="5f937-107">Um inteiro a indexar o qubit da bandeira $f$.</span><span class="sxs-lookup"><span data-stu-id="5f937-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="5f937-108">O registo do sistema $s$ que armazenará o estado quântico desejado $\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="5f937-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="5f937-109">Observações</span><span class="sxs-lookup"><span data-stu-id="5f937-109">Remarks</span></span>

<span data-ttu-id="5f937-110">Este oráculo definido por $$ O\ket {0} \_ {f}\ket {0} \_ s= \lambda\ket {1} \_ f\ket f\ket{\psi} \_ s + \sqrt{1-\lambda/^2}\ket {0} \_ f\cdots, $$ acts on the computational basis state $\ket {0} \_ {f}\ket {0} \_ s$ para criar o estado-alvo $\ket{\psi} \_ s$ com amplitude $\lambda$ na base assinalada por $\ket {1} \_ f$.</span><span class="sxs-lookup"><span data-stu-id="5f937-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="5f937-111">O primeiro parâmetro é um índice para o registo qubit de $\ket {0} \_ f$.</span><span class="sxs-lookup"><span data-stu-id="5f937-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="5f937-112">O segundo parâmetro abrangeu ambos os registos.</span><span class="sxs-lookup"><span data-stu-id="5f937-112">The second parameter encompassed both registers.</span></span>