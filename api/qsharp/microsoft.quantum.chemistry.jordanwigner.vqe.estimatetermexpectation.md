---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operação EstimativaTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224654"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="94c65-102">Operação EstimativaTermExpectation</span><span class="sxs-lookup"><span data-stu-id="94c65-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="94c65-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="94c65-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="94c65-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="94c65-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="94c65-105">Calcula a energia associada a um dado termo Jordan-Wigner Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="94c65-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="94c65-106">Description</span><span class="sxs-lookup"><span data-stu-id="94c65-106">Description</span></span>

<span data-ttu-id="94c65-107">Esta operação estima o valor de expectativa associado a cada operador de medição e multiplica-o pelo coeficiente correspondente, utilizando a amostragem.</span><span class="sxs-lookup"><span data-stu-id="94c65-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="94c65-108">Os resultados são agregados numa variável que contém a energia do termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="94c65-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="94c65-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="94c65-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="94c65-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="94c65-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="94c65-111">O unitário usado para a preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="94c65-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="94c65-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span><span class="sxs-lookup"><span data-stu-id="94c65-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="94c65-113">Os operadores de medição do termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="94c65-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="94c65-114">coeffs : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="94c65-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="94c65-115">Os coeficientes do termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="94c65-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="94c65-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94c65-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94c65-117">O número de qubits necessários para simular o sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="94c65-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="94c65-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94c65-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94c65-119">O número de amostras a utilizar para a estimativa do termo expectativa.</span><span class="sxs-lookup"><span data-stu-id="94c65-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="94c65-120">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94c65-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="94c65-121">A energia associada ao termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="94c65-121">The energy associated to the Jordan-Wigner term.</span></span>