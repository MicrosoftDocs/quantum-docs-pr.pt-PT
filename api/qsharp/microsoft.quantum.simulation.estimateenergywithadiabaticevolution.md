---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: EstimativaEnergyWithAdiabaticEvolution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 498955a712db61952d69f28cbbb4715a3efe4c5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858301"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="9c19c-102">EstimativaEnergyWithAdiabaticEvolution</span><span class="sxs-lookup"><span data-stu-id="9c19c-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="9c19c-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9c19c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9c19c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c19c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c19c-105">Realiza a preparação do Estado aplicando um num estado de `statePrepUnitary` entrada atribuído automaticamente, seguido da preparação do estado adiabático utilizando uma `adiabaticUnitary` estimativa de fase, e, finalmente, de fase, no que diz respeito `qpeUnitary` ao estado resultante utilizando a `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="9c19c-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="9c19c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9c19c-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="9c19c-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c19c-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c19c-108">Número de qubits usados para a simulação.</span><span class="sxs-lookup"><span data-stu-id="9c19c-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="9c19c-109">EstadoPrepUnitário : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9c19c-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9c19c-110">Um oráculo que representa a preparação do estado para o gerador dinâmico inicial.</span><span class="sxs-lookup"><span data-stu-id="9c19c-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="9c19c-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9c19c-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9c19c-112">Um oráculo que representa o algoritmo de evolução adiabática para ser usado para implementar as varreduras para o estado final do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="9c19c-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="9c19c-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="9c19c-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9c19c-114">Um oráculo que representa um operador unitário $U$ que representa a evolução para o tempo $\delta t$ sob um gerador dinâmico com estado de terra $\ket{\phi}$ e energia do estado do solo $E = \\ \phi,\delta t$.</span><span class="sxs-lookup"><span data-stu-id="9c19c-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="9c19c-115">phaseEstAlgorithm :[(DiscreteOracle,](xref:Microsoft.Quantum.Oracles.DiscreteOracle)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9c19c-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="9c19c-116">Uma operação que efetue a estimativa de fase numa determinada operação unitária.</span><span class="sxs-lookup"><span data-stu-id="9c19c-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="9c19c-117">Consulte [a estimativa da fase iterativa](/quantum/libraries/characterization#iterative-phase-estimation) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9c19c-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="9c19c-118">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9c19c-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9c19c-119">Uma estimativa de $\hat{\phi}$ da energia do estado do solo $\phi$ do gerador representado por $U$.</span><span class="sxs-lookup"><span data-stu-id="9c19c-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>