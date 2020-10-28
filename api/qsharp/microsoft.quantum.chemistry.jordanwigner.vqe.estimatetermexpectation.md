---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operação EstimativaTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713730"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="a11f2-102">Operação EstimativaTermExpectation</span><span class="sxs-lookup"><span data-stu-id="a11f2-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="a11f2-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="a11f2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="a11f2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a11f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a11f2-105">Calcula a energia associada a um dado termo Jordan-Wigner Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="a11f2-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="a11f2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a11f2-106">Description</span></span>

<span data-ttu-id="a11f2-107">Esta operação estima o valor de expectativa associado a cada operador de medição e multiplica-o pelo coeficiente correspondente, utilizando a amostragem.</span><span class="sxs-lookup"><span data-stu-id="a11f2-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="a11f2-108">Os resultados são agregados numa variável que contém a energia do termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="a11f2-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="a11f2-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="a11f2-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="a11f2-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="a11f2-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a11f2-111">O unitário usado para a preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="a11f2-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="a11f2-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span><span class="sxs-lookup"><span data-stu-id="a11f2-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="a11f2-113">Os operadores de medição do termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="a11f2-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="a11f2-114">coeffs : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a11f2-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a11f2-115">Os coeficientes do termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="a11f2-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="a11f2-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a11f2-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a11f2-117">O número de qubits necessários para simular o sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="a11f2-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="a11f2-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a11f2-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a11f2-119">O número de amostras a utilizar para a estimativa do termo expectativa.</span><span class="sxs-lookup"><span data-stu-id="a11f2-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="a11f2-120">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a11f2-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a11f2-121">A energia associada ao termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="a11f2-121">The energy associated to the Jordan-Wigner term.</span></span>