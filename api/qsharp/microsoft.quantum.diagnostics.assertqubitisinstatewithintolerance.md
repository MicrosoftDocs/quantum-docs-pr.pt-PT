---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202214"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="c5789-102">AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="c5789-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="c5789-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c5789-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c5789-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c5789-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c5789-105">Afirma que um qubit no estado esperado.</span><span class="sxs-lookup"><span data-stu-id="c5789-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="c5789-106">`expected` representa um vetor complexo, $\ket{\psi} = \start{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}}$.</span><span class="sxs-lookup"><span data-stu-id="c5789-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="c5789-107">O primeiro elemento dos tuples que representam cada um dos $a$, $b$ é a parte real do número complexo, enquanto o segundo é a parte imaginária.</span><span class="sxs-lookup"><span data-stu-id="c5789-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="c5789-108">O último argumento define a tolerância com que a afirmação é feita.</span><span class="sxs-lookup"><span data-stu-id="c5789-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="c5789-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5789-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="c5789-110">esperado:[(Complexo,](xref:Microsoft.Quantum.Math.Complex)[Complexo)](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c5789-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="c5789-111">Amplitudes complexas esperadas para $\ket {0} $ e $\ket {1} $, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c5789-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c5789-112">registo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c5789-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c5789-113">Qubit cujo estado deve ser afirmado.</span><span class="sxs-lookup"><span data-stu-id="c5789-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="c5789-114">Note que este qubit é assumido como separável de outros qubits atribuídos, e não emaranhado.</span><span class="sxs-lookup"><span data-stu-id="c5789-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c5789-115">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5789-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5789-116">Tolerância adídria pela qual as amplitudes reais são permitidas a desviar-se do esperado.</span><span class="sxs-lookup"><span data-stu-id="c5789-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="c5789-117">Consulte as observações abaixo para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c5789-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5789-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5789-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c5789-119">Observações</span><span class="sxs-lookup"><span data-stu-id="c5789-119">Remarks</span></span>

<span data-ttu-id="c5789-120">O seguinte código Mathematica pode ser usado para verificar expressões para mi, mx, my, mz:</span><span class="sxs-lookup"><span data-stu-id="c5789-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="c5789-121">A tolerância é a distância $L \_ {\infty}$ entre vetor real 3 dimensional (x2,x₃,x₄) definido por $\langle\psi\\rangle = x \_ 1 I + x \_ 2 X + x \_ 3 Y + x \_ 4 Z vetor de $ e real (y2,y₃,y₄) definido por ρ = y₁I + y2X + y₃Y + y₄Z onde ρ é a matriz de densidade correspondente ao estado do registo.</span><span class="sxs-lookup"><span data-stu-id="c5789-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="c5789-122">Isto só é verdade sob o pressuposto de que Tr(ρ) e Tr (/ψ⟩⟨ψ)) são ambos 1 (por exemplo, x₁ = 1/2, y₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="c5789-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="c5789-123">Se não for esse o caso, a função afirma que l∞ distância entre (x2-x₁,x₃-x₁,x₄-x₁,x₄+x₁) e (y2-y₁,y₃-y₁₄-y₁,y₄+y₁) é inferior ao parâmetro de tolerância.</span><span class="sxs-lookup"><span data-stu-id="c5789-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>