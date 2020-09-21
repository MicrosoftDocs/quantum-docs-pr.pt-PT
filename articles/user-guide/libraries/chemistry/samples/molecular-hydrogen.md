---
title: Obter estimativas do nível de energia
description: Percorre um programa de Q# amostras que estima os valores de nível de energia do hidrogénio molecular.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 05506f4099de754cd02d81fbd9200f2de091e37e
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759737"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="8c725-103">Obter estimativas do nível de energia</span><span class="sxs-lookup"><span data-stu-id="8c725-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="8c725-104">Estimar os valores dos níveis de energia é uma das principais aplicações da química quântica.</span><span class="sxs-lookup"><span data-stu-id="8c725-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="8c725-105">Este artigo descreve como pode fazer isto para o exemplo canónico do hidrogénio molecular.</span><span class="sxs-lookup"><span data-stu-id="8c725-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="8c725-106">A amostra referenciada nesta secção está [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) no repositório de amostras de química.</span><span class="sxs-lookup"><span data-stu-id="8c725-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="8c725-107">Um exemplo mais visual que traça a saída é a [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demonstração.</span><span class="sxs-lookup"><span data-stu-id="8c725-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="8c725-108">Estimando os valores energéticos do hidrogénio molecular</span><span class="sxs-lookup"><span data-stu-id="8c725-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="8c725-109">O primeiro passo é construir o Hamiltonian representando o hidrogénio molecular.</span><span class="sxs-lookup"><span data-stu-id="8c725-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="8c725-110">Embora possa construir isto usando a ferramenta NWChem, para a brevidade, esta amostra adiciona os termos Hamiltonian manualmente.</span><span class="sxs-lookup"><span data-stu-id="8c725-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="8c725-111">Simular o Hamiltonian requer a conversão dos operadores de fermião para operadores qubit.</span><span class="sxs-lookup"><span data-stu-id="8c725-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="8c725-112">Esta conversão é realizada através da codificação Jordan-Wigner da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8c725-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="8c725-113">Em seguida, passe `qSharpData` , que representa o Hamiltonian, para a `TrotterStepOracle` função.</span><span class="sxs-lookup"><span data-stu-id="8c725-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="8c725-114">`TrotterStepOracle` retorna uma operação quântica que aproxima a evolução em tempo real do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="8c725-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="8c725-115">Para obter mais informações, consulte [a dinâmica de Simulação de Hamiltonian.](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)</span><span class="sxs-lookup"><span data-stu-id="8c725-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="8c725-116">Neste ponto, você pode usar os [algoritmos](xref:microsoft.quantum.libraries.characterization) de estimativa de fase da biblioteca padrão para aprender a energia do estado do solo usando a simulação anterior.</span><span class="sxs-lookup"><span data-stu-id="8c725-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="8c725-117">Isto requer a preparação de uma boa aproximação ao estado quântico.</span><span class="sxs-lookup"><span data-stu-id="8c725-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="8c725-118">No esquema são fornecidas sugestões para tais [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) aproximações.</span><span class="sxs-lookup"><span data-stu-id="8c725-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="8c725-119">No entanto, sem estas sugestões, a abordagem padrão adiciona uma série de `hamiltonian.NElectrons` eletrões para minimizar gananciosamente as energias diagonais de um eletrão.</span><span class="sxs-lookup"><span data-stu-id="8c725-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="8c725-120">As funções e operações de estimativa de fase são fornecidas na notação DocFX no espaço de nomes [Microsoft.Quantum.Characterization.](xref:microsoft.quantum.characterization)</span><span class="sxs-lookup"><span data-stu-id="8c725-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:microsoft.quantum.characterization) namespace.</span></span>

<span data-ttu-id="8c725-121">O seguinte corte mostra como a evolução em tempo real da biblioteca de simulação de química se integra com a estimativa da fase quântica.</span><span class="sxs-lookup"><span data-stu-id="8c725-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="8c725-122">Pode agora invocar o Q# código do programa anfitrião.</span><span class="sxs-lookup"><span data-stu-id="8c725-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="8c725-123">O seguinte código C# cria um simulador de estado completo e corre `GetEnergyByTrotterization` para obter a energia do estado do solo.</span><span class="sxs-lookup"><span data-stu-id="8c725-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="8c725-124">A operação devolve dois parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8c725-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="8c725-125">`energyEst` é a estimativa da energia do estado do solo e deve ser `-1.137` próximo, em média.</span><span class="sxs-lookup"><span data-stu-id="8c725-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="8c725-126">`phaseEst` é a fase bruta devolvida pelo algoritmo de estimativa de fase.</span><span class="sxs-lookup"><span data-stu-id="8c725-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="8c725-127">Isto é útil para diagnosticar o pseudónimo quando ocorre devido a um `trotterStep` valor que é muito grande.</span><span class="sxs-lookup"><span data-stu-id="8c725-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
