---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: Função TrotterSimulationAlgorithm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: aa8338ab359441765db72a12f84a3a51e5bee3ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192541"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="c4ce0-102">Função TrotterSimulationAlgorithm</span><span class="sxs-lookup"><span data-stu-id="c4ce0-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="c4ce0-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c4ce0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c4ce0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4ce0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4ce0-105">`SimulationAlgorithm` função que utiliza uma decomposição Trotter-Suzuki para aproximar o operador de evolução temporal _exp(-iHt)_.</span><span class="sxs-lookup"><span data-stu-id="c4ce0-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="c4ce0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4ce0-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="c4ce0-107">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c4ce0-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c4ce0-108">Duração da evolução do tempo simulada num único passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="c4ce0-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c4ce0-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4ce0-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4ce0-110">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="c4ce0-110">Order of Trotter integrator.</span></span> <span data-ttu-id="c4ce0-111">Isto deve ser um ou um número par.</span><span class="sxs-lookup"><span data-stu-id="c4ce0-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="c4ce0-112">Saída : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="c4ce0-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="c4ce0-113">Um `SimulationAlgorithm` tipo.</span><span class="sxs-lookup"><span data-stu-id="c4ce0-113">A `SimulationAlgorithm` type.</span></span>