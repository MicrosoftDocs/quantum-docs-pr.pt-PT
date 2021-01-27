---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: Função ScheduleLength
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854915"
---
# <a name="schedulelength-function"></a><span data-ttu-id="47fc7-102">Função ScheduleLength</span><span class="sxs-lookup"><span data-stu-id="47fc7-102">ScheduleLength function</span></span>

<span data-ttu-id="47fc7-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="47fc7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="47fc7-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="47fc7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="47fc7-105">Devolve o número de elementos num determinado calendário de amostragem.</span><span class="sxs-lookup"><span data-stu-id="47fc7-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="47fc7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="47fc7-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="47fc7-107">calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="47fc7-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="47fc7-108">Um programa de amostragem cujo comprimento deve ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="47fc7-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="47fc7-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47fc7-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47fc7-110">O número de elementos no calendário de amostragem dado.</span><span class="sxs-lookup"><span data-stu-id="47fc7-110">The number of elements in the given sampling schedule.</span></span>