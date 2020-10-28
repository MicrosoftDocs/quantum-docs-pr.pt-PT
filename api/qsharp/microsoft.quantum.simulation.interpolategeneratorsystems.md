---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: Função InterpolateGeneratorSystems
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710566"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="3e30b-102">Função InterpolateGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="3e30b-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="3e30b-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3e30b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3e30b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e30b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e30b-105">Devolve um `TimeDependentGeneratorSystem` representante da interpolação linear entre dois `GeneratorSystem` s.</span><span class="sxs-lookup"><span data-stu-id="3e30b-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="3e30b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3e30b-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="3e30b-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3e30b-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3e30b-108">O `GeneratorSystem` início.</span><span class="sxs-lookup"><span data-stu-id="3e30b-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="3e30b-109">sistema geradorEnd : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3e30b-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3e30b-110">O `GeneratorSystem` fim.</span><span class="sxs-lookup"><span data-stu-id="3e30b-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="3e30b-111">Saída : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3e30b-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="3e30b-112">Um `TimeDependentGeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada, com peso $(1-s)$ `generatorSystemStart` e peso $s$ em `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="3e30b-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e30b-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3e30b-113">See Also</span></span>

- [<span data-ttu-id="3e30b-114">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="3e30b-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="3e30b-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="3e30b-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)