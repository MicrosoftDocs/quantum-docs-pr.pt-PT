---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: Função de anulação da 20daplificação da 1.90da ção
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721829"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="0fd44-102">Função de anulação da 20daplificação da 1.90da ção</span><span class="sxs-lookup"><span data-stu-id="0fd44-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="0fd44-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="0fd44-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="0fd44-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0fd44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0fd44-105">Amplificação de amplitude alheia por oráculos para reflexões parciais.</span><span class="sxs-lookup"><span data-stu-id="0fd44-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0fd44-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0fd44-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="0fd44-107">fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="0fd44-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="0fd44-108">Fases de reflexões parciais</span><span class="sxs-lookup"><span data-stu-id="0fd44-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="0fd44-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="0fd44-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="0fd44-110">Oráculo unitário $A$ que prepara estado de arranque auxiliar</span><span class="sxs-lookup"><span data-stu-id="0fd44-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="0fd44-111">signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="0fd44-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="0fd44-112">Oráculo unitário $O$ do tipo `ObliviousOracle` que atua conjuntamente no registo auxiliar e do sistema</span><span class="sxs-lookup"><span data-stu-id="0fd44-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="0fd44-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fd44-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0fd44-114">Índice para registo de bandeira de um único qubit</span><span class="sxs-lookup"><span data-stu-id="0fd44-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="0fd44-115">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="0fd44-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0fd44-116">Uma operação que implementa amplificação de amplitude alheia baseada em reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="0fd44-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="0fd44-117">Observações</span><span class="sxs-lookup"><span data-stu-id="0fd44-117">Remarks</span></span>

<span data-ttu-id="0fd44-118">Isto impõe condições mais rigorosas sob a forma dos estados auxiliares de início e alvo do que em `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="0fd44-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="0fd44-119">Presume-se que $A\ket {0} \_ f\ket {0} \_ a= \ket{\text{start}} \_ {fa}$ prepara o estado de início auxiliar $\ket{\text{start}} \_ {fa}$ da base computacional $\ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0fd44-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="0fd44-120">Presume-se que o estado-alvo é marcado por $\ket {1} \_ f$.</span><span class="sxs-lookup"><span data-stu-id="0fd44-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="0fd44-121">Presume-se que \start{align} O\ket{\text{start}} \_ {fa}\ket{\psi} \_ s= \lambda\ket {1} \_ f\ket f\ket{\text{anything}} \_ a\ket{text{target}} \_ u\ket{\psi} \_ s + \sqrt{1-\\lambda/^2}ket\f\f\cdots, {0} \_ \end{align} para alguns $U unitários$.</span><span class="sxs-lookup"><span data-stu-id="0fd44-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>