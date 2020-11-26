---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: Operação AproximadamentePrepareArbitraryState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > ApproximatelyPrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 9e1b172258acd0cb09b824a773e7e79d44fec20c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193714"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="1d202-102">Operação AproximadamentePrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="1d202-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="1d202-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1d202-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1d202-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1d202-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="1d202-105">AproximadamentePrepareArbitraryState foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="1d202-105">ApproximatelyPrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="1d202-106">Por favor, use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="1d202-106">Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="1d202-107">Dado um conjunto de coeficientes e um registo quântico codificado pouco endiano, prepara um estado nesse registo descrito pelos coeficientes dados, até uma certa tolerância de aproximação.</span><span class="sxs-lookup"><span data-stu-id="1d202-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1d202-108">Description</span><span class="sxs-lookup"><span data-stu-id="1d202-108">Description</span></span>

<span data-ttu-id="1d202-109">Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="1d202-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="1d202-110">Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como</span><span class="sxs-lookup"><span data-stu-id="1d202-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="1d202-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{{j} \sqrt{\sum_{j=0}^{2^n-1} [r_j/^2} }.</span><span class="sxs-lookup"><span data-stu-id="1d202-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="1d202-112">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="1d202-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="1d202-113">Entrada</span><span class="sxs-lookup"><span data-stu-id="1d202-113">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="1d202-114">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1d202-114">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1d202-115">A tolerância de aproximação a utilizar na preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="1d202-115">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="1d202-116">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="1d202-116">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="1d202-117">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="1d202-117">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="1d202-118">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="1d202-118">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="1d202-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d202-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1d202-120">O número de codificação do registo qubit está em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="1d202-120">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="1d202-121">Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.</span><span class="sxs-lookup"><span data-stu-id="1d202-121">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d202-122">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d202-122">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1d202-123">Observações</span><span class="sxs-lookup"><span data-stu-id="1d202-123">Remarks</span></span>

<span data-ttu-id="1d202-124">Coeficientes de entrada negativos $r_j < 0$ serão tratados como se positivos com valor $/ r_j</span><span class="sxs-lookup"><span data-stu-id="1d202-124">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="1d202-125">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="1d202-125">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="1d202-126">Referências</span><span class="sxs-lookup"><span data-stu-id="1d202-126">References</span></span>

- <span data-ttu-id="1d202-127">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="1d202-127">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="1d202-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1d202-128">See Also</span></span>

- [<span data-ttu-id="1d202-129">Microsoft.Quantum.Preparation.ApproximatePrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="1d202-129">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)