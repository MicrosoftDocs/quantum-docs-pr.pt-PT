---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: Função GetGeneratorSystemFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724556"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="e1e15-102">Função GetGeneratorSystemFunction</span><span class="sxs-lookup"><span data-stu-id="e1e15-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="e1e15-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e1e15-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e1e15-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1e15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1e15-105">Recupera a `GeneratorIndex` função num `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="e1e15-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="e1e15-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e1e15-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e1e15-107">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e1e15-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e1e15-108">O `GeneratorSystem` interesse.</span><span class="sxs-lookup"><span data-stu-id="e1e15-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="e1e15-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e1e15-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e1e15-110">Uma função que indexa cada `GeneratorIndex` termo num Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="e1e15-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1e15-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e1e15-111">See Also</span></span>

- [<span data-ttu-id="e1e15-112">Microsoft.Quantum.Simulation.GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="e1e15-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="e1e15-113">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e1e15-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)