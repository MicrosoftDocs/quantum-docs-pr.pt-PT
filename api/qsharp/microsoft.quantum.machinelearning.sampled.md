---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Função amostrada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722428"
---
# <a name="sampled-function"></a><span data-ttu-id="17b4b-102">Função amostrada</span><span class="sxs-lookup"><span data-stu-id="17b4b-102">Sampled function</span></span>

<span data-ttu-id="17b4b-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="17b4b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="17b4b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17b4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17b4b-105">Amostras de uma determinada matriz, usando o horário dado.</span><span class="sxs-lookup"><span data-stu-id="17b4b-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="17b4b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="17b4b-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="17b4b-107">calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="17b4b-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="17b4b-108">Um horário a utilizar em valores de amostragem.</span><span class="sxs-lookup"><span data-stu-id="17b4b-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="17b4b-109">valores : 'T[]</span><span class="sxs-lookup"><span data-stu-id="17b4b-109">values : 'T[]</span></span>

<span data-ttu-id="17b4b-110">Uma variedade de valores a serem amostrados.</span><span class="sxs-lookup"><span data-stu-id="17b4b-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="17b4b-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="17b4b-111">Output : 'T[]</span></span>

<span data-ttu-id="17b4b-112">Uma série de elementos de valores, seguindo o horário dado.</span><span class="sxs-lookup"><span data-stu-id="17b4b-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="17b4b-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="17b4b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17b4b-114">'T</span><span class="sxs-lookup"><span data-stu-id="17b4b-114">'T</span></span>

