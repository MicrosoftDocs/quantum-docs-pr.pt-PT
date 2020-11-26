---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223702"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="44ea5-102">AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="44ea5-102">AssertProbInt operation</span></span>

<span data-ttu-id="44ea5-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="44ea5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="44ea5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44ea5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44ea5-105">Afirma que a probabilidade de um estado específico de um registo quântico tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="44ea5-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="44ea5-106">Description</span><span class="sxs-lookup"><span data-stu-id="44ea5-106">Description</span></span>

<span data-ttu-id="44ea5-107">Dado um $n$-qubit estado quântico $\ket{\psi}=\sum^{2^n-1}___j=0}\alpha_j \ket{j}$, afirma que a probabilidade $\alpha_j^2$ do estado $\ket{j}$ indexado por $j$ tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="44ea5-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="44ea5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="44ea5-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="44ea5-109">estadoIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44ea5-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44ea5-110">O índice $j$ do estado $\ket{j}$ representado por um `LittleEndian` registo.</span><span class="sxs-lookup"><span data-stu-id="44ea5-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="44ea5-111">esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44ea5-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44ea5-112">O valor esperado de $\alpha_j^2$.</span><span class="sxs-lookup"><span data-stu-id="44ea5-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="44ea5-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="44ea5-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="44ea5-114">O registo qubit que armazena $\ket{\psi}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="44ea5-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="44ea5-115">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44ea5-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44ea5-116">Tolerância absoluta na diferença entre real e esperado.</span><span class="sxs-lookup"><span data-stu-id="44ea5-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44ea5-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44ea5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

