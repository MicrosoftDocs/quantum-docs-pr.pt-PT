---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateCP
title: Preparar operação DoERAteraryStateCP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 1e293057f8b549dc57817cdce350e50e2b91682a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856912"
---
# <a name="preparearbitrarystatecp-operation"></a><span data-ttu-id="5815c-102">Preparar operação DoERAteraryStateCP</span><span class="sxs-lookup"><span data-stu-id="5815c-102">PrepareArbitraryStateCP operation</span></span>

<span data-ttu-id="5815c-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5815c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5815c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5815c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5815c-105">Dado um conjunto de coeficientes e um pequeno registo quântico codificado, prepara um estado nesse registo descrito pelos coeficientes.</span><span class="sxs-lookup"><span data-stu-id="5815c-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateCP (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5815c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="5815c-106">Description</span></span>

<span data-ttu-id="5815c-107">Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="5815c-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="5815c-108">Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como</span><span class="sxs-lookup"><span data-stu-id="5815c-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="5815c-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{j} \{sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span><span class="sxs-lookup"><span data-stu-id="5815c-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="5815c-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="5815c-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="5815c-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="5815c-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="5815c-112">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="5815c-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="5815c-113">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="5815c-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="5815c-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="5815c-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="5815c-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5815c-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5815c-116">O número de codificação do registo qubit está em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="5815c-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="5815c-117">Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.</span><span class="sxs-lookup"><span data-stu-id="5815c-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5815c-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5815c-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5815c-119">Observações</span><span class="sxs-lookup"><span data-stu-id="5815c-119">Remarks</span></span>

<span data-ttu-id="5815c-120">Coeficientes de entrada negativos $r_j < 0$ serão tratados como positivos com valor de $|r_j|$.</span><span class="sxs-lookup"><span data-stu-id="5815c-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="5815c-121">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="5815c-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="5815c-122">Referências</span><span class="sxs-lookup"><span data-stu-id="5815c-122">References</span></span>

- <span data-ttu-id="5815c-123">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="5815c-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="5815c-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5815c-124">See Also</span></span>

- [<span data-ttu-id="5815c-125">Microsoft.Quantum.Preparation.ApproximatePrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="5815c-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)