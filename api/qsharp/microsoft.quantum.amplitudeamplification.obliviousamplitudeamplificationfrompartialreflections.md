---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections
title: Função De AntidesplitudeAmplificaçãoFromPartialReflections
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromPartialReflections
qsharp.summary: Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.
ms.openlocfilehash: e00578867f14947571fd595bdf876bc271c3d485
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847201"
---
# <a name="obliviousamplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="67f70-102">Função De AntidesplitudeAmplificaçãoFromPartialReflections</span><span class="sxs-lookup"><span data-stu-id="67f70-102">ObliviousAmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="67f70-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="67f70-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="67f70-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67f70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67f70-105">Devolve uma amplificação unitária que implementa amplificação de amplitude alheia especificando para reflexões parciais.</span><span class="sxs-lookup"><span data-stu-id="67f70-105">Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="67f70-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="67f70-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="67f70-107">fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="67f70-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="67f70-108">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="67f70-108">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="67f70-109">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="67f70-109">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="67f70-110">signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="67f70-110">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>





## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="67f70-111">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="67f70-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

