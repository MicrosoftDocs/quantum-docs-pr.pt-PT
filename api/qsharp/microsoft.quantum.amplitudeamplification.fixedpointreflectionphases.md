---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Função FixedPointReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191453"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="5f78c-102">Função FixedPointReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="5f78c-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="5f78c-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5f78c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5f78c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f78c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f78c-105">Calcula as fases de reflexão parcial para amplificação da amplitude de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="5f78c-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="5f78c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5f78c-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="5f78c-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5f78c-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5f78c-108">Número de consultas ao oráculo de preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="5f78c-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="5f78c-109">Deve ser um número inteiro estranho.</span><span class="sxs-lookup"><span data-stu-id="5f78c-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="5f78c-110">successMin : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5f78c-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5f78c-111">Probabilidade mínima de sucesso.</span><span class="sxs-lookup"><span data-stu-id="5f78c-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="5f78c-112">Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="5f78c-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="5f78c-113">Conjunto de fases que podem ser usadas na implementação do algoritmo quântico de amplificação de amplitude fixa.</span><span class="sxs-lookup"><span data-stu-id="5f78c-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="5f78c-114">Referências</span><span class="sxs-lookup"><span data-stu-id="5f78c-114">References</span></span>

<span data-ttu-id="5f78c-115">Utilizamos as fases em "Amplificação de Amplitude de Ponto Fixo com um Número Ideal de Consultas"</span><span class="sxs-lookup"><span data-stu-id="5f78c-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="5f78c-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Consulte também "Metodologia de portões quânticos compostos"</span><span class="sxs-lookup"><span data-stu-id="5f78c-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="5f78c-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) para fases no `RotationPhases` formato.</span><span class="sxs-lookup"><span data-stu-id="5f78c-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>