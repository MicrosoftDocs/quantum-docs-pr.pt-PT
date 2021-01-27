---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operação Exp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819017"
---
# <a name="exp-operation"></a><span data-ttu-id="23fa5-102">Operação Exp</span><span class="sxs-lookup"><span data-stu-id="23fa5-102">Exp operation</span></span>

<span data-ttu-id="23fa5-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="23fa5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="23fa5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="23fa5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="23fa5-105">Aplica o exponencial de um operador pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="23fa5-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="23fa5-106">\start{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}} \end{align} onde $P_i$ é o elemento $i$th de `paulis` , e onde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="23fa5-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="23fa5-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="23fa5-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="23fa5-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="23fa5-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="23fa5-109">Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.</span><span class="sxs-lookup"><span data-stu-id="23fa5-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="23fa5-110">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23fa5-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23fa5-111">Ângulo sobre o operador pauli multi-qubit dado pelo qual o registo-alvo deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="23fa5-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="23fa5-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="23fa5-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="23fa5-113">Registe-se para aplicar a rotação dada.</span><span class="sxs-lookup"><span data-stu-id="23fa5-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23fa5-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23fa5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

