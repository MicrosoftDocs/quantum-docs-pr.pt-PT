---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: Função MultiplyGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229159"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="e3c87-102">Função MultiplyGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e3c87-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="e3c87-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e3c87-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e3c87-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3c87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3c87-105">Multiplica o coeficiente de todos os termos em `GeneratorSystem` um .</span><span class="sxs-lookup"><span data-stu-id="e3c87-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e3c87-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3c87-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="e3c87-107">multiplicador : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3c87-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3c87-108">O multiplicador do coeficiente.</span><span class="sxs-lookup"><span data-stu-id="e3c87-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e3c87-109">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e3c87-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e3c87-110">O `GeneratorSystem` a ser multiplicado.</span><span class="sxs-lookup"><span data-stu-id="e3c87-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="e3c87-111">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e3c87-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e3c87-112">Um `GeneratorSystem` sistema representando um sistema com coeficientes um fator `multiplier` maior.</span><span class="sxs-lookup"><span data-stu-id="e3c87-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3c87-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e3c87-113">See Also</span></span>

- [<span data-ttu-id="e3c87-114">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e3c87-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)