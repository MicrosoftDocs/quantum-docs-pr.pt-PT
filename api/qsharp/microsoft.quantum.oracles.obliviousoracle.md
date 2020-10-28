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
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="95e22-102">Tipo definido pelo utilizador Doósforo</span><span class="sxs-lookup"><span data-stu-id="95e22-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="95e22-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="95e22-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="95e22-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95e22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95e22-105">Representa um oráculo para amplificação de amplitude alheia.</span><span class="sxs-lookup"><span data-stu-id="95e22-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="95e22-106">As entradas para o oráculo $O$ são:</span><span class="sxs-lookup"><span data-stu-id="95e22-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="95e22-107">O registo da Ancilla $a dólares em que $O$ atua.</span><span class="sxs-lookup"><span data-stu-id="95e22-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="95e22-108">O registo do sistema $s$ em que é aplicado o $U$ unitário desejado, pós-seleccionado no registo $a$ estando no estado $\ket{t} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="95e22-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="95e22-109">Observações</span><span class="sxs-lookup"><span data-stu-id="95e22-109">Remarks</span></span>

<span data-ttu-id="95e22-110">Este oráculo definido por $$ O\ket{s} \_ a\ket{\psi} \_ s= \lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-\lambda/^2}ket{t^\perp} \_ a\cdots $$ atua no estado de ancilla $\ket{s} \_ a$ para implementar o $U$ unitário em qualquer estado do sistema $\ket{\psi} \_ s$ com amplitude $\lambda$ na base sinalizada por $\ket{t} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="95e22-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="95e22-111">O primeiro parâmetro é o registo qubit de $\ket{s} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="95e22-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="95e22-112">O segundo parâmetro é o registo qubit de $\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="95e22-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>