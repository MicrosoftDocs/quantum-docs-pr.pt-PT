---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Função amostrada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854952"
---
# <a name="sampled-function"></a><span data-ttu-id="80941-102">Função amostrada</span><span class="sxs-lookup"><span data-stu-id="80941-102">Sampled function</span></span>

<span data-ttu-id="80941-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="80941-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="80941-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="80941-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="80941-105">Amostras de uma determinada matriz, usando o horário dado.</span><span class="sxs-lookup"><span data-stu-id="80941-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="80941-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="80941-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="80941-107">calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="80941-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="80941-108">Um horário a utilizar em valores de amostragem.</span><span class="sxs-lookup"><span data-stu-id="80941-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="80941-109">valores : 'T[]</span><span class="sxs-lookup"><span data-stu-id="80941-109">values : 'T[]</span></span>

<span data-ttu-id="80941-110">Uma variedade de valores a serem amostrados.</span><span class="sxs-lookup"><span data-stu-id="80941-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="80941-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="80941-111">Output : 'T[]</span></span>

<span data-ttu-id="80941-112">Uma série de elementos de valores, seguindo o horário dado.</span><span class="sxs-lookup"><span data-stu-id="80941-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="80941-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="80941-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80941-114">'T</span><span class="sxs-lookup"><span data-stu-id="80941-114">'T</span></span>

