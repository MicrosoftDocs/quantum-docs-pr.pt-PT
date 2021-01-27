---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843406"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="daec1-102">AssertProbInt</span><span class="sxs-lookup"><span data-stu-id="daec1-102">AssertProbInt operation</span></span>

<span data-ttu-id="daec1-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="daec1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="daec1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="daec1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="daec1-105">Afirma que a probabilidade de um estado específico de um registo quântico tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="daec1-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="daec1-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="daec1-106">Description</span></span>

<span data-ttu-id="daec1-107">Dado um $n$-qubit estado quântico $\ket{\psi}=\sum^{2^n-1}_j=0}\alpha_j \ket{j}$, afirma que a probabilidade $|\alpha_j|^2$ do estado $\ket{j}} indexado por $j$ tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="daec1-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="daec1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="daec1-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="daec1-109">estadoIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="daec1-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="daec1-110">O índice $j$ do estado $\ket{j}$ representado por um `LittleEndian` registo.</span><span class="sxs-lookup"><span data-stu-id="daec1-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="daec1-111">esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="daec1-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="daec1-112">O valor esperado de $|\alpha_j|^2$.</span><span class="sxs-lookup"><span data-stu-id="daec1-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="daec1-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="daec1-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="daec1-114">O registo qubit que armazena $\ket{\psi}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="daec1-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="daec1-115">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="daec1-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="daec1-116">Tolerância absoluta na diferença entre real e esperado.</span><span class="sxs-lookup"><span data-stu-id="daec1-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="daec1-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="daec1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="daec1-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="daec1-118">Example</span></span>

<span data-ttu-id="daec1-119">Suponha que o `qubits` registo codifica um estado quântico de 3 qubits $\ket{\psi}=\sqrt{1/8}\ket {0} +\sqrt{7/8}\ket {6} $ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="daec1-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="daec1-120">Isto significa que o número diz $\ket {0} \equiv\ket {0} {0} \ket \ket {0} \ket $ e $\ket {6} \equiv\ket {0} {1} \ket \ket \ket {1} \ket $.</span><span class="sxs-lookup"><span data-stu-id="daec1-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="daec1-121">Em seguida, as seguintes afirmações sucedem- se:</span><span class="sxs-lookup"><span data-stu-id="daec1-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```