---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Função StandardReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721731"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="fbf97-102">Função StandardReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="fbf97-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="fbf97-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="fbf97-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="fbf97-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbf97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbf97-105">Calcula as fases de reflexão parcial para amplificação de amplitude padrão.</span><span class="sxs-lookup"><span data-stu-id="fbf97-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="fbf97-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fbf97-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="fbf97-107">niterações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbf97-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbf97-108">Número de iterações de amplificação de amplitude para gerar fases de reflexão parcial para.</span><span class="sxs-lookup"><span data-stu-id="fbf97-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="fbf97-109">Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="fbf97-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="fbf97-110">Uma operação que implementa fases especificadas como reflexões parciais</span><span class="sxs-lookup"><span data-stu-id="fbf97-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="fbf97-111">Observações</span><span class="sxs-lookup"><span data-stu-id="fbf97-111">Remarks</span></span>

<span data-ttu-id="fbf97-112">Todas as fases são $\pi$, exceto para o primeiro reflexo sobre o estado de início e a última reflexão sobre o estado alvo, que são $0$.</span><span class="sxs-lookup"><span data-stu-id="fbf97-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>