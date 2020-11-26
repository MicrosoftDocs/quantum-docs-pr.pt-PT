---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Função de Prescrição DePreparaçõesComplexCoficientes
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210374"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="ee240-102">Função de Prescrição DePreparaçõesComplexCoficientes</span><span class="sxs-lookup"><span data-stu-id="ee240-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="ee240-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ee240-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ee240-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee240-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="ee240-105">StatePreparationComplexCoefficients foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="ee240-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="ee240-106">Por favor, use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="ee240-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="ee240-107">Devolve uma operação que prepara um estado quântico específico.</span><span class="sxs-lookup"><span data-stu-id="ee240-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="ee240-108">A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0...0}$...$.$.$.$.$.$$.$$$$$$$$$-qubit base de base computacional estado $\ket{0...$$....$.$...</span><span class="sxs-lookup"><span data-stu-id="ee240-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="ee240-109">A ação de U num registo recém-atribuído é dada por $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{{{r_j sum_{{{{2}}.</span><span class="sxs-lookup"><span data-stu-id="ee240-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="ee240-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="ee240-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ee240-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="ee240-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="ee240-112">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="ee240-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="ee240-113">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="ee240-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="ee240-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="ee240-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="ee240-115">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="ee240-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ee240-116">Uma operação unitária de preparação do estado $U$.</span><span class="sxs-lookup"><span data-stu-id="ee240-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee240-117">Observações</span><span class="sxs-lookup"><span data-stu-id="ee240-117">Remarks</span></span>

<span data-ttu-id="ee240-118">Coeficientes de entrada negativos $r_j < 0$ serão tratados como se positivos com valor $/ r_j</span><span class="sxs-lookup"><span data-stu-id="ee240-118">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="ee240-119">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="ee240-119">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>