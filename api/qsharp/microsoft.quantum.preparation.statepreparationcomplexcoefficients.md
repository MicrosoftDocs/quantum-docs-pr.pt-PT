---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Função de Prescrição DePreparaçõesComplexCoficientes
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722907"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="8a136-102">Função de Prescrição DePreparaçõesComplexCoficientes</span><span class="sxs-lookup"><span data-stu-id="8a136-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="8a136-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8a136-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8a136-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a136-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a136-105">Devolve uma operação que prepara um estado quântico específico.</span><span class="sxs-lookup"><span data-stu-id="8a136-105">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="8a136-106">A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0...0}$...$.$.$.$.$.$$.$$$$$$$$$-qubit base de base computacional estado $\ket{0...$$....$.$...</span><span class="sxs-lookup"><span data-stu-id="8a136-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="8a136-107">A ação de U num registo recém-atribuído é dada por $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{{{r_j sum_{{{{2}}.</span><span class="sxs-lookup"><span data-stu-id="8a136-107">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="8a136-108">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="8a136-108">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8a136-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a136-109">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="8a136-110">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="8a136-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="8a136-111">Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$.</span><span class="sxs-lookup"><span data-stu-id="8a136-111">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="8a136-112">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="8a136-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="8a136-113">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8a136-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8a136-114">Uma operação unitária de preparação do estado $U$.</span><span class="sxs-lookup"><span data-stu-id="8a136-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a136-115">Observações</span><span class="sxs-lookup"><span data-stu-id="8a136-115">Remarks</span></span>

<span data-ttu-id="8a136-116">Coeficientes de entrada negativos $r_j < 0$ serão tratados como se positivos com valor $/ r_j</span><span class="sxs-lookup"><span data-stu-id="8a136-116">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="8a136-117">`coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="8a136-117">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>