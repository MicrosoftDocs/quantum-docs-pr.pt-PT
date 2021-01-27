---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Função de Prescrição DePreparaçõesComplexCoficientes
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: c16df0fe075b15cff745a6b7d5b79aac39c14d09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856140"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="f279c-102">Função de Prescrição DePreparaçõesComplexCoficientes</span><span class="sxs-lookup"><span data-stu-id="f279c-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="f279c-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f279c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f279c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f279c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f279c-105">StatePreparationComplexCoefficients foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="f279c-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="f279c-106">Por favor, use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f279c-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="f279c-107">Devolve uma operação que prepara um estado quântico específico.</span><span class="sxs-lookup"><span data-stu-id="f279c-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="f279c-108">A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0...0}$...$$.$-qubit base de base computacional estado $\ket{0...$$...</span><span class="sxs-lookup"><span data-stu-id="f279c-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="f279c-109">A ação de U num registo recém-atribuído é dada por $$ \start{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^2^2^0^2^0^2^0^2^0^2^0 n-1}r_j e^{i t_j}\ket{j}}{|r_j| sum_{{}2}}</span><span class="sxs-lookup"><span data-stu-id="f279c-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="f279c-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="f279c-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f279c-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="f279c-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="f279c-112">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="f279c-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="f279c-113">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="f279c-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="f279c-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="f279c-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="f279c-115">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="f279c-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f279c-116">Uma operação unitária de preparação do estado $U$.</span><span class="sxs-lookup"><span data-stu-id="f279c-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="f279c-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f279c-117">Example</span></span>

<span data-ttu-id="f279c-118">O seguinte corte prepara o estado quântico $\ket{\psi}=e^{i 0.1}\sqrt{1/8}\ket {0} +\sqrt{7/8}\ket {2} $ in the qubit register `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="f279c-118">The following snippet prepares the quantum state $\ket{\psi}=e^{i 0.1}\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let phases = [0.1, 0.0, 0.0, 0.0];
mutable complexNumbers = new ComplexPolar[4];
for (idx in 0..3) {
    set complexNumbers[idx] = ComplexPolar(amplitudes[idx], phases[idx]);
}
let op = StatePreparationComplexCoefficients(complexNumbers);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="f279c-119">Observações</span><span class="sxs-lookup"><span data-stu-id="f279c-119">Remarks</span></span>

<span data-ttu-id="f279c-120">Coeficientes de entrada negativos $r_j < 0$ serão tratados como positivos com valor de $|r_j|$.</span><span class="sxs-lookup"><span data-stu-id="f279c-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f279c-121">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="f279c-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>