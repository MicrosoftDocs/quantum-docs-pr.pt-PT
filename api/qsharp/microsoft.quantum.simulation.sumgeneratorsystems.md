---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: Função SumGeneratorSystems
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 0e64d2b599c55c19711208670030fd01e09aff7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851021"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="56c76-102">Função SumGeneratorSystems</span><span class="sxs-lookup"><span data-stu-id="56c76-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="56c76-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="56c76-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="56c76-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56c76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56c76-105">Adiciona vários `GeneratorSystem` s para criar um novo GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="56c76-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="56c76-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="56c76-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="56c76-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="56c76-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="56c76-108">Uma matriz de `GeneratorSystem[]` tipo.</span><span class="sxs-lookup"><span data-stu-id="56c76-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="56c76-109">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="56c76-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="56c76-110">Um `GeneratorSystem` sistema que representa um sistema que é a soma dos sistemas geradores de entrada.</span><span class="sxs-lookup"><span data-stu-id="56c76-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="56c76-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="56c76-111">See Also</span></span>

- [<span data-ttu-id="56c76-112">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="56c76-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)