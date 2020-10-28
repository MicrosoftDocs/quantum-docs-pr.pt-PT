---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: Função ScheduleLength
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 77538984fbd7334712df423b991ef43ce31ed849
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722403"
---
# <a name="schedulelength-function"></a><span data-ttu-id="3ded4-102">Função ScheduleLength</span><span class="sxs-lookup"><span data-stu-id="3ded4-102">ScheduleLength function</span></span>

<span data-ttu-id="3ded4-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3ded4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3ded4-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ded4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ded4-105">Devolve o número de elementos num determinado calendário de amostragem.</span><span class="sxs-lookup"><span data-stu-id="3ded4-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="3ded4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ded4-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="3ded4-107">calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="3ded4-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="3ded4-108">Um programa de amostragem cujo comprimento deve ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="3ded4-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="3ded4-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ded4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ded4-110">O número de elementos no calendário de amostragem dado.</span><span class="sxs-lookup"><span data-stu-id="3ded4-110">The number of elements in the given sampling schedule.</span></span>