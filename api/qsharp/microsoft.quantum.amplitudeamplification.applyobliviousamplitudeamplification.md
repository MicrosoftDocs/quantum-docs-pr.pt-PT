---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operação ApplyObliviousAmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721882"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="b763d-102">Operação ApplyObliviousAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="b763d-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="b763d-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b763d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b763d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b763d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b763d-105">Amplificação de amplitude alheia especificando reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="b763d-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b763d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b763d-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="b763d-107">fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b763d-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b763d-108">Fases de reflexões parciais</span><span class="sxs-lookup"><span data-stu-id="b763d-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="b763d-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b763d-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b763d-110">Operador de reflexão sobre o estado inicial do registo auxiliar</span><span class="sxs-lookup"><span data-stu-id="b763d-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="b763d-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b763d-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b763d-112">Operador de reflexão sobre estado-alvo do registo auxiliar</span><span class="sxs-lookup"><span data-stu-id="b763d-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="b763d-113">signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="b763d-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="b763d-114">Oráculo unitário $O de$ de tipo `ObliviousOracle` que atua conjuntamente nos registos auxiliares e do sistema.</span><span class="sxs-lookup"><span data-stu-id="b763d-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="b763d-115">AuxiliarRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b763d-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b763d-116">Registo auxiliar</span><span class="sxs-lookup"><span data-stu-id="b763d-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="b763d-117">sistemaRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b763d-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b763d-118">Registo do sistema</span><span class="sxs-lookup"><span data-stu-id="b763d-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="b763d-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b763d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b763d-120">Observações</span><span class="sxs-lookup"><span data-stu-id="b763d-120">Remarks</span></span>

<span data-ttu-id="b763d-121">Dado um determinado estado de início auxiliar $\ket{\text{start}} \_ a$, um estado-alvo auxiliar específico $\ket{\text{target}} \_ a$, e qualquer estado do sistema $\ket{\psi} \_ s$, suponhamos que \begin{align} O\ket{\text{start}} \_ a\ket{\psi} \_ s= \lambda\ket{\text{target}} \_ a U\ket{\psi} \_ s + \sqrt{1-\lambda/^2}\ket{\text{target}\\perp} \_ a\cdots \end{} para alguns $U</span><span class="sxs-lookup"><span data-stu-id="b763d-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="b763d-122">Através de uma sequência de reflexões sobre os estados de início e alvo no registo auxiliar intercalado por aplicações de `signalOracle` e seus adjacentes, a probabilidade de sucesso da aplicação de U pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="b763d-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="b763d-123">Na maioria dos casos, `auxiliaryRegister` é inicializado no estado $\ket{\text{start}} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="b763d-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="b763d-124">Referências</span><span class="sxs-lookup"><span data-stu-id="b763d-124">References</span></span>

<span data-ttu-id="b763d-125">Consulte</span><span class="sxs-lookup"><span data-stu-id="b763d-125">See</span></span>

- <span data-ttu-id="b763d-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) para a versão padrão.</span><span class="sxs-lookup"><span data-stu-id="b763d-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="b763d-127">Consulte</span><span class="sxs-lookup"><span data-stu-id="b763d-127">See</span></span>
- <span data-ttu-id="b763d-128">[ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) para uma generalização a reflexões parciais.</span><span class="sxs-lookup"><span data-stu-id="b763d-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>