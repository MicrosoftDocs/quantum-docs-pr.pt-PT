---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operação Exp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 2eea29ec08260ea9cee1bafde80a0942e06f5abc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212414"
---
# <a name="exp-operation"></a><span data-ttu-id="55bed-102">Operação Exp</span><span class="sxs-lookup"><span data-stu-id="55bed-102">Exp operation</span></span>

<span data-ttu-id="55bed-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="55bed-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="55bed-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="55bed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="55bed-105">Aplica o exponencial de um operador pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="55bed-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="55bed-106">\start{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}} \end{align} onde $P_i$ é o elemento $i$th de `paulis` , e onde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="55bed-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="55bed-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="55bed-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="55bed-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="55bed-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="55bed-109">Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.</span><span class="sxs-lookup"><span data-stu-id="55bed-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="55bed-110">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="55bed-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="55bed-111">Ângulo sobre o operador pauli multi-qubit dado pelo qual o registo-alvo deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="55bed-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="55bed-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="55bed-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="55bed-113">Registe-se para aplicar a rotação dada.</span><span class="sxs-lookup"><span data-stu-id="55bed-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55bed-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55bed-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

