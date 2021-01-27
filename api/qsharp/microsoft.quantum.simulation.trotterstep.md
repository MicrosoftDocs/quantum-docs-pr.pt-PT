---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: Função TrotterStep
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 4c0e7dd89b1beae9fb6a35ae5b8d16e09d355ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854711"
---
# <a name="trotterstep-function"></a><span data-ttu-id="19344-102">Função TrotterStep</span><span class="sxs-lookup"><span data-stu-id="19344-102">TrotterStep function</span></span>

<span data-ttu-id="19344-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="19344-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="19344-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19344-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19344-105">Implementa um único passo de evolução temporal pelo sistema descrito numa `EvolutionGenerator` decomposição Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="19344-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="19344-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="19344-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="19344-107">EvolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="19344-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="19344-108">Uma descrição completa do sistema a ser simulado.</span><span class="sxs-lookup"><span data-stu-id="19344-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="19344-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19344-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19344-110">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="19344-110">Order of Trotter integrator.</span></span> <span data-ttu-id="19344-111">Isto deve ser um ou um número par.</span><span class="sxs-lookup"><span data-stu-id="19344-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="19344-112">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="19344-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="19344-113">Duração da evolução do tempo simulada num único passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="19344-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="19344-114">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="19344-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="19344-115">Funcionamento unitário que se aproxima de um único passo de evolução temporal durante a duração `trotterStepSize` .</span><span class="sxs-lookup"><span data-stu-id="19344-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="19344-116">Observações</span><span class="sxs-lookup"><span data-stu-id="19344-116">Remarks</span></span>

<span data-ttu-id="19344-117">Para mais informações sobre a decomposição Trotter-Suzuki, consulte [a composição ordenada pelo tempo](/quantum/libraries/control-flow#time-ordered-composition).</span><span class="sxs-lookup"><span data-stu-id="19344-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>