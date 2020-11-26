---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Função de EstadoPreparaçõesPositiveCoefficients
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193255"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="b5268-102">Função de EstadoPreparaçõesPositiveCoefficients</span><span class="sxs-lookup"><span data-stu-id="b5268-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="b5268-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b5268-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b5268-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5268-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="b5268-105">Os EstadosPreparationPositiveCoefficients foram depreciados.</span><span class="sxs-lookup"><span data-stu-id="b5268-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="b5268-106">Por favor, use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="b5268-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="b5268-107">Devolve uma operação que prepara o estado quântico.</span><span class="sxs-lookup"><span data-stu-id="b5268-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="b5268-108">A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes positivos $\alpha_j\ge 0$ do estado de base computacional $n$-qubit $\ket{0...0}$..$.$.$.$$$$$-00}$.$$$$-qubit basis basis state $\ket{0...$$.$.$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$.$$$$$$$$$$$$$$$$$$$00}$.$$$$$$$-qubit basis basis state $\ket{0...0}$.</span><span class="sxs-lookup"><span data-stu-id="b5268-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="b5268-109">A ação de U num registo recém-atribuído é dada por $$ \start{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^^^{2^n-1}\alpha_j \ket{j}}{{\sqrt{\sum_{j=0}^{2^n-1}[\alpha_j^2}}}</span><span class="sxs-lookup"><span data-stu-id="b5268-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="b5268-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="b5268-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b5268-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="b5268-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="b5268-112">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b5268-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b5268-113">Matriz de até $2^n$ coeficientes $\alpha_j$.</span><span class="sxs-lookup"><span data-stu-id="b5268-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="b5268-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="b5268-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="b5268-115">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="b5268-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b5268-116">Uma operação unitária de preparação do estado $U$.</span><span class="sxs-lookup"><span data-stu-id="b5268-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5268-117">Observações</span><span class="sxs-lookup"><span data-stu-id="b5268-117">Remarks</span></span>

<span data-ttu-id="b5268-118">Coeficientes de entrada negativos $\alpha_j < 0$ serão tratados como se positivo com valor $\alpha_j.$.</span><span class="sxs-lookup"><span data-stu-id="b5268-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="b5268-119">`coefficients` serão acolchoados com elementos $\alpha_j = 0,0$ se forem especificados menos de $2^n$</span><span class="sxs-lookup"><span data-stu-id="b5268-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>