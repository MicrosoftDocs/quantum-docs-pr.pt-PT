---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: Função TimeDependentTrotterSimulationAlgorithm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858363"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="fb06e-102">Função TimeDependentTrotterSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="fb06e-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="fb06e-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fb06e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fb06e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb06e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb06e-105">`TimeDependentSimulationAlgorithm` função que usa uma decomposição Trotter-Suzuki para aproximar um operador unitário que resolve a equação schrodinger dependente do tempo.</span><span class="sxs-lookup"><span data-stu-id="fb06e-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="fb06e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fb06e-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="fb06e-107">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb06e-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb06e-108">Duração da evolução do tempo simulada num único passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="fb06e-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="fb06e-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb06e-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb06e-110">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="fb06e-110">Order of Trotter integrator.</span></span> <span data-ttu-id="fb06e-111">Isto deve ser um ou um número par.</span><span class="sxs-lookup"><span data-stu-id="fb06e-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="fb06e-112">Saída : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="fb06e-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="fb06e-113">Um `TimeDependentSimulationAlgorithm` tipo.</span><span class="sxs-lookup"><span data-stu-id="fb06e-113">A `TimeDependentSimulationAlgorithm` type.</span></span>