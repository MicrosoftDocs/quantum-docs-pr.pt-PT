---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: Preparar Operação Do Estado De Preparação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18f45da601b02fc5f83936b086323e31a66fc20b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724041"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="80b4d-102">Preparar Operação Do Estado De Preparação</span><span class="sxs-lookup"><span data-stu-id="80b4d-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="80b4d-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="80b4d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="80b4d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80b4d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80b4d-105">Dado um conjunto de coeficientes e um pequeno registo quântico codificado, prepara um estado nesse registo descrito pelos coeficientes.</span><span class="sxs-lookup"><span data-stu-id="80b4d-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="80b4d-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="80b4d-106">Description</span></span>

<span data-ttu-id="80b4d-107">Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="80b4d-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="80b4d-108">Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como</span><span class="sxs-lookup"><span data-stu-id="80b4d-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="80b4d-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{{j} \sqrt{\sum_{j=0}^{2^n-1} [r_j/^2} }.</span><span class="sxs-lookup"><span data-stu-id="80b4d-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="80b4d-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="80b4d-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="80b4d-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="80b4d-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="80b4d-112">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="80b4d-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="80b4d-113">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="80b4d-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="80b4d-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="80b4d-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="80b4d-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="80b4d-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="80b4d-116">O número de codificação do registo qubit está em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="80b4d-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="80b4d-117">Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.</span><span class="sxs-lookup"><span data-stu-id="80b4d-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80b4d-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80b4d-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="80b4d-119">Observações</span><span class="sxs-lookup"><span data-stu-id="80b4d-119">Remarks</span></span>

<span data-ttu-id="80b4d-120">Coeficientes de entrada negativos $r_j < 0$ serão tratados como se positivos com valor $/ r_j</span><span class="sxs-lookup"><span data-stu-id="80b4d-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="80b4d-121">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="80b4d-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="80b4d-122">Referências</span><span class="sxs-lookup"><span data-stu-id="80b4d-122">References</span></span>

- <span data-ttu-id="80b4d-123">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="80b4d-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="80b4d-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="80b4d-124">See Also</span></span>

- [<span data-ttu-id="80b4d-125">Microsoft.Quantum.Preparation.ApproximatePrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="80b4d-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)