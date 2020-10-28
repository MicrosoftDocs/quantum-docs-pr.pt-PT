---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: Operação ExpFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711490"
---
# <a name="expfrac-operation"></a><span data-ttu-id="447e5-102">Operação ExpFrac</span><span class="sxs-lookup"><span data-stu-id="447e5-102">ExpFrac operation</span></span>

<span data-ttu-id="447e5-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="447e5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="447e5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="447e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="447e5-105">Aplica o exponencial de um operador pauli multi-qubit com um argumento dado por uma fração diádica.</span><span class="sxs-lookup"><span data-stu-id="447e5-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="447e5-106">\start{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} onde $P_i$ é o elemento $i$th de `paulis` , e onde $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="447e5-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="447e5-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="447e5-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="447e5-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="447e5-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="447e5-109">Matriz de valores pauli de um único qubit indicando os fatores do produto tensor em cada qubit.</span><span class="sxs-lookup"><span data-stu-id="447e5-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="447e5-110">numerador : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="447e5-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="447e5-111">Numerador ($k$) na representação da fração dedódica do ângulo pelo qual o registo qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="447e5-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="447e5-112">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="447e5-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="447e5-113">Potência de dois ($n$) especificando o denominador do ângulo pelo qual o registo qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="447e5-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="447e5-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="447e5-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="447e5-115">Registe-se para aplicar a rotação dada.</span><span class="sxs-lookup"><span data-stu-id="447e5-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="447e5-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="447e5-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

