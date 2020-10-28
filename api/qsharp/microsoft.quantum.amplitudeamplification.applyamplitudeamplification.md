---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Operação ApplyAmplitudeAmplificação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721927"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="1b713-102">Operação ApplyAmplitudeAmplificação</span><span class="sxs-lookup"><span data-stu-id="1b713-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="1b713-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1b713-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1b713-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b713-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b713-105">Aplica amplificação de amplitude num dado registo, utilizando um determinado conjunto de fases e oráculos para refletir sobre os estados iniciais e finais.</span><span class="sxs-lookup"><span data-stu-id="1b713-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1b713-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b713-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="1b713-107">fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="1b713-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="1b713-108">Um conjunto de fases descrevendo os reflexos parciais em cada passo do algoritmo de amplificação da amplitude.</span><span class="sxs-lookup"><span data-stu-id="1b713-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="1b713-109">Veja @"microsoft.quantum.amplitudeamplification.standardreflectionphases" por exemplo.</span><span class="sxs-lookup"><span data-stu-id="1b713-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="1b713-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="1b713-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="1b713-111">Um oráculo que reflete sobre o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="1b713-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="1b713-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="1b713-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="1b713-113">Um oráculo que reflete sobre o desejado estado final.</span><span class="sxs-lookup"><span data-stu-id="1b713-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1b713-114">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1b713-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1b713-115">Um registo para efetuar a amplificação da amplitude.</span><span class="sxs-lookup"><span data-stu-id="1b713-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b713-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b713-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

