---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: Função InterpolateGeneratorSystemsImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709435"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="0d93e-102">Função InterpolateGeneratorSystemsImpl</span><span class="sxs-lookup"><span data-stu-id="0d93e-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="0d93e-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0d93e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0d93e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d93e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d93e-105">Interpola linearmente entre dois `GeneratorSystems` de acordo com um parâmetro de programação entre `s` 0 e 1 (inclusive).</span><span class="sxs-lookup"><span data-stu-id="0d93e-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="0d93e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d93e-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="0d93e-107">horário : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d93e-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d93e-108">Um parâmetro de agenda $s\in[0,1]$.</span><span class="sxs-lookup"><span data-stu-id="0d93e-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="0d93e-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="0d93e-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="0d93e-110">O `GeneratorSystem` início.</span><span class="sxs-lookup"><span data-stu-id="0d93e-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="0d93e-111">sistema geradorEnd : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="0d93e-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="0d93e-112">O `GeneratorSystem` fim.</span><span class="sxs-lookup"><span data-stu-id="0d93e-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="0d93e-113">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="0d93e-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="0d93e-114">Um `GeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada, com peso $(1-s)$ `generatorSystemStart` e peso $s$ em `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="0d93e-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d93e-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0d93e-115">See Also</span></span>

- [<span data-ttu-id="0d93e-116">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="0d93e-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)