---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: Operação CNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722669"
---
# <a name="cnot-operation"></a><span data-ttu-id="d952a-102">Operação CNOT</span><span class="sxs-lookup"><span data-stu-id="d952a-102">CNOT operation</span></span>

<span data-ttu-id="d952a-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d952a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d952a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d952a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d952a-105">Aplica o portão NÃO controlado (CNOT) a um par de qubits.</span><span class="sxs-lookup"><span data-stu-id="d952a-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="d952a-106">\start{align} \operatorname{CNOT} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 10 \\ \\ & 0 & 1 & 0 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="d952a-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="d952a-107">onde as linhas e colunas são ordenadas como no guia de conceitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="d952a-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d952a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d952a-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="d952a-109">controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d952a-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d952a-110">Controlo qubit para o portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="d952a-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d952a-111">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d952a-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d952a-112">Qubit de alvo para o portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="d952a-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d952a-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d952a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d952a-114">Observações</span><span class="sxs-lookup"><span data-stu-id="d952a-114">Remarks</span></span>

<span data-ttu-id="d952a-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="d952a-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```