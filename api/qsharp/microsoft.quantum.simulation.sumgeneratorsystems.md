---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: Função SumGeneratorSystems
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719879"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="1ce16-102">Função SumGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="1ce16-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="1ce16-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1ce16-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1ce16-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ce16-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ce16-105">Adiciona vários `GeneratorSystem` s para criar um novo GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="1ce16-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="1ce16-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ce16-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="1ce16-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="1ce16-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="1ce16-108">Uma matriz de `GeneratorSystem[]` tipo.</span><span class="sxs-lookup"><span data-stu-id="1ce16-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="1ce16-109">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="1ce16-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="1ce16-110">Um `GeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada.</span><span class="sxs-lookup"><span data-stu-id="1ce16-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ce16-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1ce16-111">See Also</span></span>

- [<span data-ttu-id="1ce16-112">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="1ce16-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)