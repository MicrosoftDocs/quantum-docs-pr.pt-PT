---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Medir operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 804ae72ed2d5302b14011b737b7ed3ad2b9a14ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212295"
---
# <a name="measure-operation"></a><span data-ttu-id="82802-102">Medir operação</span><span class="sxs-lookup"><span data-stu-id="82802-102">Measure operation</span></span>

<span data-ttu-id="82802-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="82802-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="82802-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="82802-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="82802-105">Realiza uma medição articular de um ou mais qubits nas bases pauli especificadas.</span><span class="sxs-lookup"><span data-stu-id="82802-105">Performs a joint measurement of one or more qubits in the specified Pauli bases.</span></span>

<span data-ttu-id="82802-106">O resultado da saída é dado pela distribuição: \start{align} \Pr(\texttt{Zero} / \ket{\psi}) = \frac12 \braket\ \psi \mid\ \boldone + P_0 \otimes P_1 \otimes \otimes \otimes \otimes P_{N-1} \right \) \\end{align} onde $P_i$ é o elemento $i$th de `bases` , e onde $N = \texttt{Length}(\texttt{bases})$.</span><span class="sxs-lookup"><span data-stu-id="82802-106">The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$.</span></span>
<span data-ttu-id="82802-107">Ou seja, a medição devolve um `Result` $d$ de modo a que o valor do efeito de medição observado seja $(-1)^d$.</span><span class="sxs-lookup"><span data-stu-id="82802-107">That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.</span></span>

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="82802-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="82802-108">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="82802-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="82802-109">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="82802-110">Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.</span><span class="sxs-lookup"><span data-stu-id="82802-110">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="82802-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="82802-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="82802-112">Registo de qubits a medir.</span><span class="sxs-lookup"><span data-stu-id="82802-112">Register of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="82802-113">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="82802-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="82802-114">`Zero` se o $+1$ eigenvalue for observado, e `One` se o $-1$ eigenvalue for observado.</span><span class="sxs-lookup"><span data-stu-id="82802-114">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="82802-115">Observações</span><span class="sxs-lookup"><span data-stu-id="82802-115">Remarks</span></span>

<span data-ttu-id="82802-116">Se a matriz de base e a matriz de qubits forem diferentes comprimentos, então a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="82802-116">If the basis array and qubit array are different lengths, then the operation will fail.</span></span>