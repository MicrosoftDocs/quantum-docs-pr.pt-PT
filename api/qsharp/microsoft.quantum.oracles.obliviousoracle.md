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
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="4a04a-102">Tipo definido pelo utilizador Doósforo</span><span class="sxs-lookup"><span data-stu-id="4a04a-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="4a04a-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4a04a-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4a04a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a04a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a04a-105">Representa um oráculo para amplificação de amplitude alheia.</span><span class="sxs-lookup"><span data-stu-id="4a04a-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="4a04a-106">As entradas para o oráculo $O$ são:</span><span class="sxs-lookup"><span data-stu-id="4a04a-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="4a04a-107">O registo da Ancilla $a dólares em que $O$ atua.</span><span class="sxs-lookup"><span data-stu-id="4a04a-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="4a04a-108">O registo do sistema $s$ em que é aplicado o $U$ unitário desejado, pós-seleccionado no registo $a$ estando no estado $\ket{t} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="4a04a-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="4a04a-109">Observações</span><span class="sxs-lookup"><span data-stu-id="4a04a-109">Remarks</span></span>

<span data-ttu-id="4a04a-110">Este oráculo definido por $$ O\ket{s} \_ a\ket{\psi} \_ s= \lambda\ket{t} \_ a U\ket{\psi} \_ s + \sqrt{1-|\lambda|^2}ket{t^\ket{\ket{t^\sqrt{1-|\lambda|^2}ket{t^\perp} \_ a\cdots $$ acts on the ancilla state $\ket{s} \_ a$ to implement the unitary $U$ on any system state $\ket{\psi} \_ s$ com amplitude $\lambda$ na base sinalizada por $\ket{t} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="4a04a-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="4a04a-111">O primeiro parâmetro é o registo qubit de $\ket{s} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="4a04a-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="4a04a-112">O segundo parâmetro é o registo qubit de $\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="4a04a-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>