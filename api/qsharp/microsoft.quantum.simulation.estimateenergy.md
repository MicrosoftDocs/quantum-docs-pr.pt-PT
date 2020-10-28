---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: Estimativa OperaçãoEnergia
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722053"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="8958f-102">Estimativa OperaçãoEnergia</span><span class="sxs-lookup"><span data-stu-id="8958f-102">EstimateEnergy operation</span></span>

<span data-ttu-id="8958f-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8958f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8958f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8958f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8958f-105">Executa a preparação do Estado aplicando uma `statePrepUnitary` numa estimativa de fase de fase de entrada atribuída automaticamente no que diz respeito ao estado resultante utilizando `qpeUnitary` a `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="8958f-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="8958f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8958f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="8958f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8958f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8958f-108">Número de qubits usados para realizar simulação.</span><span class="sxs-lookup"><span data-stu-id="8958f-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="8958f-109">EstadoPrepUnitário : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8958f-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8958f-110">Um oráculo que representa a preparação do estado para o gerador dinâmico inicial.</span><span class="sxs-lookup"><span data-stu-id="8958f-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="8958f-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8958f-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8958f-112">Um oráculo que representa um operador unitário $U$ que representa a evolução para o tempo $\delta t$ sob um gerador dinâmico com estado de terra $\ket{\phi}$ e energia do estado do solo $E = \\ \phi,\delta t$.</span><span class="sxs-lookup"><span data-stu-id="8958f-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="8958f-113">phaseEstAlgorithm :[(DiscreteOracle,](xref:Microsoft.Quantum.Oracles.DiscreteOracle)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8958f-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="8958f-114">Uma operação que efetue a estimativa de fase numa determinada operação unitária.</span><span class="sxs-lookup"><span data-stu-id="8958f-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="8958f-115">Consulte [a estimativa da fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8958f-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="8958f-116">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8958f-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8958f-117">Uma estimativa de $\hat{\phi}$ da energia do estado do solo $\phi$ da energia do estado terrestre do gerador representada por $U$.</span><span class="sxs-lookup"><span data-stu-id="8958f-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>