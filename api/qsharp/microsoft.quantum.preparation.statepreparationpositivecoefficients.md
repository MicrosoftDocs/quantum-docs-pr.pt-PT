---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Função de EstadoPreparaçõesPositiveCoefficients
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722893"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="80186-102">Função de EstadoPreparaçõesPositiveCoefficients</span><span class="sxs-lookup"><span data-stu-id="80186-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="80186-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="80186-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="80186-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80186-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80186-105">Devolve uma operação que prepara o estado quântico.</span><span class="sxs-lookup"><span data-stu-id="80186-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="80186-106">A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes positivos $\alpha_j\ge 0$ do estado de base computacional $n$-qubit $\ket{0...0}$..$.$.$.$$$$$-00}$.$$$$-qubit basis basis state $\ket{0...$$.$.$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$.$$$$$$$$$$$$$$$$$$$00}$.$$$$$$$-qubit basis basis state $\ket{0...0}$.</span><span class="sxs-lookup"><span data-stu-id="80186-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="80186-107">A ação de U num registo recém-atribuído é dada por $$ \start{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^^^{2^n-1}\alpha_j \ket{j}}{{\sqrt{\sum_{j=0}^{2^n-1}[\alpha_j^2}}}</span><span class="sxs-lookup"><span data-stu-id="80186-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="80186-108">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="80186-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="80186-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="80186-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="80186-110">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="80186-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="80186-111">Matriz de até $2^n$ coeficientes $\alpha_j$.</span><span class="sxs-lookup"><span data-stu-id="80186-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="80186-112">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="80186-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="80186-113">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="80186-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="80186-114">Uma operação unitária de preparação do estado $U$.</span><span class="sxs-lookup"><span data-stu-id="80186-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="80186-115">Observações</span><span class="sxs-lookup"><span data-stu-id="80186-115">Remarks</span></span>

<span data-ttu-id="80186-116">Coeficientes de entrada negativos $\alpha_j < 0$ serão tratados como se positivo com valor $\alpha_j.$.</span><span class="sxs-lookup"><span data-stu-id="80186-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="80186-117">`coefficients` serão acolchoados com elementos $\alpha_j = 0,0$ se forem especificados menos de $2^n$</span><span class="sxs-lookup"><span data-stu-id="80186-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>