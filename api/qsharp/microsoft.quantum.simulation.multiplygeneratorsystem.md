---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: Função MultiplyGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: cebd08c86ad8a3793ba7d0e9ce241d7a1ef046ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858502"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="e8945-102">Função MultiplyGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e8945-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="e8945-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e8945-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e8945-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8945-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8945-105">Multiplica o coeficiente de todos os termos em `GeneratorSystem` um .</span><span class="sxs-lookup"><span data-stu-id="e8945-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e8945-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e8945-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="e8945-107">multiplicador : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8945-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8945-108">O multiplicador do coeficiente.</span><span class="sxs-lookup"><span data-stu-id="e8945-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e8945-109">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e8945-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e8945-110">O `GeneratorSystem` a ser multiplicado.</span><span class="sxs-lookup"><span data-stu-id="e8945-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="e8945-111">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e8945-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e8945-112">Um `GeneratorSystem` sistema representando um sistema com coeficientes um fator `multiplier` maior.</span><span class="sxs-lookup"><span data-stu-id="e8945-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8945-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e8945-113">See Also</span></span>

- [<span data-ttu-id="e8945-114">Microsoft.Quantum.Simulation.GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="e8945-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)