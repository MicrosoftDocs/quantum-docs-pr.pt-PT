---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP
title: Operação AproximadamentePrepareArbitraryStateCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 44352a4d6325c128539351695fb14d3706ce842f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226541"
---
# <a name="approximatelypreparearbitrarystatecp-operation"></a><span data-ttu-id="d56b7-102">Operação AproximadamentePrepareArbitraryStateCP</span><span class="sxs-lookup"><span data-stu-id="d56b7-102">ApproximatelyPrepareArbitraryStateCP operation</span></span>

<span data-ttu-id="d56b7-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d56b7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d56b7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d56b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d56b7-105">Dado um conjunto de coeficientes e um registo quântico codificado pouco endiano, prepara um estado nesse registo descrito pelos coeficientes dados, até uma certa tolerância de aproximação.</span><span class="sxs-lookup"><span data-stu-id="d56b7-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryStateCP (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d56b7-106">Description</span><span class="sxs-lookup"><span data-stu-id="d56b7-106">Description</span></span>

<span data-ttu-id="d56b7-107">Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="d56b7-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="d56b7-108">Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como</span><span class="sxs-lookup"><span data-stu-id="d56b7-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="d56b7-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{{j} \sqrt{\sum_{j=0}^{2^n-1} [r_j/^2} }.</span><span class="sxs-lookup"><span data-stu-id="d56b7-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="d56b7-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="d56b7-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="d56b7-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="d56b7-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="d56b7-112">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d56b7-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d56b7-113">A tolerância de aproximação a utilizar na preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="d56b7-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="d56b7-114">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="d56b7-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="d56b7-115">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="d56b7-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="d56b7-116">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="d56b7-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d56b7-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d56b7-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d56b7-118">O número de codificação do registo qubit está em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="d56b7-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="d56b7-119">Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.</span><span class="sxs-lookup"><span data-stu-id="d56b7-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d56b7-120">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d56b7-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d56b7-121">Observações</span><span class="sxs-lookup"><span data-stu-id="d56b7-121">Remarks</span></span>

<span data-ttu-id="d56b7-122">Coeficientes de entrada negativos $r_j < 0$ serão tratados como se positivos com valor $/ r_j</span><span class="sxs-lookup"><span data-stu-id="d56b7-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="d56b7-123">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="d56b7-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="d56b7-124">Referências</span><span class="sxs-lookup"><span data-stu-id="d56b7-124">References</span></span>

- <span data-ttu-id="d56b7-125">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="d56b7-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>