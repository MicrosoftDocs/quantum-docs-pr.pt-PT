---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721366"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="9c74f-102">AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="9c74f-102">AssertProbInt operation</span></span>

<span data-ttu-id="9c74f-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9c74f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9c74f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c74f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c74f-105">Afirma que a probabilidade de um estado específico de um registo quântico tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="9c74f-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="9c74f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="9c74f-106">Description</span></span>

<span data-ttu-id="9c74f-107">Dado um $n$-qubit estado quântico $\ket{\psi}=\sum^{2^n-1}___j=0}\alpha_j \ket{j}$, afirma que a probabilidade $\alpha_j^2$ do estado $\ket{j}$ indexado por $j$ tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="9c74f-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="9c74f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9c74f-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="9c74f-109">estadoIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c74f-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c74f-110">O índice $j$ do estado $\ket{j}$ representado por um `LittleEndian` registo.</span><span class="sxs-lookup"><span data-stu-id="9c74f-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="9c74f-111">esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9c74f-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9c74f-112">O valor esperado de $\alpha_j^2$.</span><span class="sxs-lookup"><span data-stu-id="9c74f-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9c74f-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9c74f-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9c74f-114">O registo qubit que armazena $\ket{\psi}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="9c74f-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9c74f-115">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9c74f-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9c74f-116">Tolerância absoluta na diferença entre real e esperado.</span><span class="sxs-lookup"><span data-stu-id="9c74f-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c74f-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c74f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

