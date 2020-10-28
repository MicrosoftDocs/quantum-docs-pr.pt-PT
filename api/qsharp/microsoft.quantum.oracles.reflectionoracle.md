---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido pelo utilizador Reflexoracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724209"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="1e483-102">Tipo definido pelo utilizador Reflexoracle</span><span class="sxs-lookup"><span data-stu-id="1e483-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="1e483-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="1e483-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="1e483-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e483-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e483-105">Representa um oráculo de reflexão.</span><span class="sxs-lookup"><span data-stu-id="1e483-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="1e483-106">Um oráculo de reflexão, $O$, tem entradas:</span><span class="sxs-lookup"><span data-stu-id="1e483-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="1e483-107">A fase $\phi$ para rodar o subespaço refletido.</span><span class="sxs-lookup"><span data-stu-id="1e483-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="1e483-108">O registo de qubits para realizar a reflexão dada.</span><span class="sxs-lookup"><span data-stu-id="1e483-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="1e483-109">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="1e483-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="1e483-110">ApplyReflection :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="1e483-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="1e483-111">Observações</span><span class="sxs-lookup"><span data-stu-id="1e483-111">Remarks</span></span>

<span data-ttu-id="1e483-112">Este oráculo $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ realiza um reflexo parcial por uma fase $\phi$ sobre um único estado puro $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="1e483-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>