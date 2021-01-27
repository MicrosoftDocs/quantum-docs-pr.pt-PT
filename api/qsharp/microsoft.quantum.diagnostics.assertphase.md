---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operação AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830070"
---
# <a name="assertphase-operation"></a><span data-ttu-id="366b0-102">Operação AssertPhase</span><span class="sxs-lookup"><span data-stu-id="366b0-102">AssertPhase operation</span></span>

<span data-ttu-id="366b0-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="366b0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="366b0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="366b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="366b0-105">Afirma que a fase de um estado de superposição igual tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="366b0-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="366b0-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="366b0-106">Description</span></span>

<span data-ttu-id="366b0-107">Esta operação afirma que a fase $\phi$ de um estado quântico que pode ser expressa como $\frac{e^{i t}sqrt {2} }(e^{i\phi}ket {0} + e^-i\phi}\ket {1} )$ para algum real arbitrário $t$ tem o valor esperado.</span><span class="sxs-lookup"><span data-stu-id="366b0-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="366b0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="366b0-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="366b0-109">esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="366b0-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="366b0-110">O valor esperado de $\phi \in (\pi,\pi]$.</span><span class="sxs-lookup"><span data-stu-id="366b0-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="366b0-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="366b0-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="366b0-112">O qubit que armazena o estado esperado.</span><span class="sxs-lookup"><span data-stu-id="366b0-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="366b0-113">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="366b0-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="366b0-114">Tolerância absoluta na diferença entre real e esperado.</span><span class="sxs-lookup"><span data-stu-id="366b0-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="366b0-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="366b0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="366b0-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="366b0-116">Example</span></span>

<span data-ttu-id="366b0-117">A afirmação seguinte tem sucesso: `qubit` está em estado $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket {0} +e^{i 0.5}sqrt{1/2}\ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="366b0-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="366b0-118">`qubit` está em estado $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket {0} +e^{-i 0,5}\sqrt{1/2}\ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="366b0-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="366b0-119">`qubit` está em estado $\ket{\psi}=e^{-i 2.2}sqrt{1/2}\ket {0} +e^{i 0.2}\sqrt{1/2}\ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="366b0-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`