---
title: Obter estimativas do nível de energia
description: Caminhe por um programa Q# de amostra que estima os valores do nível de energia do hidrogénio molecular.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 3242d8c6dc6fad2bd99055027dd7ce4ec3510ff4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907312"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="3f22f-103">Obter estimativas do nível de energia</span><span class="sxs-lookup"><span data-stu-id="3f22f-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="3f22f-104">Estimar os valores dos níveis de energia é uma das principais aplicações da química quântica.</span><span class="sxs-lookup"><span data-stu-id="3f22f-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="3f22f-105">Aqui, esboçamos como isto pode ser feito para o exemplo canónico do hidrogénio molecular.</span><span class="sxs-lookup"><span data-stu-id="3f22f-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="3f22f-106">A amostra referida nesta secção é `MolecularHydrogen` no repositório de amostras de química.</span><span class="sxs-lookup"><span data-stu-id="3f22f-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="3f22f-107">Um exemplo mais visual que traça a saída é a demonstração `MolecularHydrogenGUI`.</span><span class="sxs-lookup"><span data-stu-id="3f22f-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="3f22f-108">O nosso primeiro passo é construir o Hamiltonian representando o hidrogénio molecular.</span><span class="sxs-lookup"><span data-stu-id="3f22f-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="3f22f-109">Embora isto possa ser construído através da ferramenta NWChem, adicionamos manualmente termos Hamiltonian para brevidade nesta amostra.</span><span class="sxs-lookup"><span data-stu-id="3f22f-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="3f22f-110">Simular o Hamiltonian exige que convertamos os operadores de fermion em operadores qubit.</span><span class="sxs-lookup"><span data-stu-id="3f22f-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="3f22f-111">Esta conversão é realizada através da codificação Jordan-Wigner da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="3f22f-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="3f22f-112">Passamos agora a `qSharpData` representando o Hamiltonian para a função `TrotterStepOracle` na simulação da [dinâmica hamiltoniana.](xref:microsoft.quantum.libraries.standard.algorithms)</span><span class="sxs-lookup"><span data-stu-id="3f22f-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="3f22f-113">`TrotterStepOracle` retorna a uma operação quântica que se aproxima da evolução real do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="3f22f-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="3f22f-114">Podemos agora usar os algoritmos de estimativa de fase da biblioteca padrão para aprender a energia do estado terrestre usando a simulação acima.</span><span class="sxs-lookup"><span data-stu-id="3f22f-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="3f22f-115">Isto requer preparar uma boa aproximação ao estado quântico do solo.</span><span class="sxs-lookup"><span data-stu-id="3f22f-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="3f22f-116">Sugestões para tais aproximações são fornecidas no esquema `Broombridge`, mas sem estas sugestões, a abordagem padrão adiciona uma série de eletrões `hamiltonian.NElectrons` para minimizar gananciosamente as energias diagonais de um só eletrão.</span><span class="sxs-lookup"><span data-stu-id="3f22f-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="3f22f-117">As funções e operações de estimativa de fase estão localizadas no espaço de [nome microsoft.Quantum.Characterization](xref:microsoft.quantum.characterization in DocFX notation).</span><span class="sxs-lookup"><span data-stu-id="3f22f-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="3f22f-118">O seguinte corte mostra como a produção real de evolução do tempo pela biblioteca de simulação de química pode ser integrada com a estimativa de fase quântica.</span><span class="sxs-lookup"><span data-stu-id="3f22f-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="3f22f-119">Este código Q# pode agora ser invocado do programa de condutor.</span><span class="sxs-lookup"><span data-stu-id="3f22f-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="3f22f-120">No seguinte, criamos um simulador de estado inteiro e executamos `GetEnergyByTrotterization` para obter a energia do estado terrestre.</span><span class="sxs-lookup"><span data-stu-id="3f22f-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="3f22f-121">Note que dois parâmetros são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="3f22f-121">Note that two parameters are returned.</span></span> <span data-ttu-id="3f22f-122">`energyEst` é a estimativa da energia do estado terrestre, devendo rondar `-1.137`, em média.</span><span class="sxs-lookup"><span data-stu-id="3f22f-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="3f22f-123">`phaseEst` é a fase bruta devolvida pelo algoritmo de estimativa de fase, e é útil para diagnosticar quando o pseudónimo ocorre devido a um `trotterStep` que é muito grande.</span><span class="sxs-lookup"><span data-stu-id="3f22f-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
