---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Função StandardReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191130"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="38b39-102">Função StandardReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="38b39-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="38b39-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="38b39-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="38b39-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38b39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38b39-105">Calcula as fases de reflexão parcial para amplificação de amplitude padrão.</span><span class="sxs-lookup"><span data-stu-id="38b39-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="38b39-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="38b39-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="38b39-107">niterações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="38b39-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="38b39-108">Número de iterações de amplificação de amplitude para gerar fases de reflexão parcial para.</span><span class="sxs-lookup"><span data-stu-id="38b39-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="38b39-109">Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="38b39-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="38b39-110">Uma operação que implementa fases especificadas como reflexões parciais</span><span class="sxs-lookup"><span data-stu-id="38b39-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="38b39-111">Observações</span><span class="sxs-lookup"><span data-stu-id="38b39-111">Remarks</span></span>

<span data-ttu-id="38b39-112">Todas as fases são $\pi$, exceto para o primeiro reflexo sobre o estado de início e a última reflexão sobre o estado alvo, que são $0$.</span><span class="sxs-lookup"><span data-stu-id="38b39-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>