---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido pelo utilizador Reflexoracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226660"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="e2fa1-102">Tipo definido pelo utilizador Reflexoracle</span><span class="sxs-lookup"><span data-stu-id="e2fa1-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="e2fa1-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e2fa1-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e2fa1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2fa1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2fa1-105">Representa um oráculo de reflexão.</span><span class="sxs-lookup"><span data-stu-id="e2fa1-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="e2fa1-106">Um oráculo de reflexão, $O$, tem entradas:</span><span class="sxs-lookup"><span data-stu-id="e2fa1-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="e2fa1-107">A fase $\phi$ para rodar o subespaço refletido.</span><span class="sxs-lookup"><span data-stu-id="e2fa1-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="e2fa1-108">O registo de qubits para realizar a reflexão dada.</span><span class="sxs-lookup"><span data-stu-id="e2fa1-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="e2fa1-109">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="e2fa1-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="e2fa1-110">ApplyReflection :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="e2fa1-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="e2fa1-111">Observações</span><span class="sxs-lookup"><span data-stu-id="e2fa1-111">Remarks</span></span>

<span data-ttu-id="e2fa1-112">Este oráculo $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ realiza um reflexo parcial por uma fase $\phi$ sobre um único estado puro $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="e2fa1-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>