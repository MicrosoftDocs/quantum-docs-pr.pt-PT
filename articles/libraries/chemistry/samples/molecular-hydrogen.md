---
title: Obtendo estimativas de nível de energia | Microsoft Docs
description: Obtendo documentos de estimativas de nível de energia
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 32f18ea479a2c65eee2b0e16788dc9f0fabd5372
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185550"
---
## <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="511ca-103">Obtendo estimativas de nível de energia</span><span class="sxs-lookup"><span data-stu-id="511ca-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="511ca-104">Estimar os valores dos níveis de energia é um dos principais aplicativos da quantum química.</span><span class="sxs-lookup"><span data-stu-id="511ca-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="511ca-105">Aqui, descrevemos como isso pode ser executado para o exemplo canônico de molecular Hydrogen.</span><span class="sxs-lookup"><span data-stu-id="511ca-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="511ca-106">O exemplo referenciado nesta seção é `MolecularHydrogen` no repositório de exemplos de química.</span><span class="sxs-lookup"><span data-stu-id="511ca-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="511ca-107">Um exemplo mais visual que plota a saída é a `MolecularHydrogenGUI` demonstração.</span><span class="sxs-lookup"><span data-stu-id="511ca-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="511ca-108">Nossa primeira etapa é construir o Hamiltonian que representa o molecular Hydrogen.</span><span class="sxs-lookup"><span data-stu-id="511ca-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="511ca-109">Embora isso possa ser construído por meio da ferramenta NWChem, adicionamos manualmente os termos de Hamiltonian para brevidade neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="511ca-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

<span data-ttu-id="511ca-110">A simulação do Hamiltonian exige a conversão dos operadores Fermion em operadores qubit.</span><span class="sxs-lookup"><span data-stu-id="511ca-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="511ca-111">Essa conversão é executada por meio da codificação Jordânia-Wigner da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="511ca-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

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

<span data-ttu-id="511ca-112">Agora, passamos o `qSharpData` representando o Hamiltonian para a função `TrotterStepOracle` na [simulação do Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span><span class="sxs-lookup"><span data-stu-id="511ca-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="511ca-113">`TrotterStepOracle` retorna uma operação Quantum que aproxima a evolução em tempo real do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="511ca-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

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

<span data-ttu-id="511ca-114">Agora podemos usar os algoritmos de estimativa de fase da biblioteca padrão para aprender a energia de estado terrestre usando a simulação acima.</span><span class="sxs-lookup"><span data-stu-id="511ca-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="511ca-115">Isso requer a preparação de uma boa aproximação para o estado de aterramento do Quantum.</span><span class="sxs-lookup"><span data-stu-id="511ca-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="511ca-116">As sugestões para essas aproximaçãos são fornecidas no esquema de `Broombridge`, mas essas sugestões estão ausentes, a abordagem padrão adiciona um número de `hamiltonian.NElectrons` elétrons ao greedily minimizar o termo diagonal um-.</span><span class="sxs-lookup"><span data-stu-id="511ca-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="511ca-117">As funções e operações de estimativa de fase estão localizadas no [namespace Microsoft. Quantum. caracterization](xref:microsoft.quantum.characterization in DocFX notation).</span><span class="sxs-lookup"><span data-stu-id="511ca-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="511ca-118">O trecho a seguir mostra como a saída de evolução em tempo real da biblioteca de simulação de química pode ser integrada com a estimativa de fase Quantum.</span><span class="sxs-lookup"><span data-stu-id="511ca-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

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

<span data-ttu-id="511ca-119">Este código de Q # agora pode ser invocado a partir do programa de driver.</span><span class="sxs-lookup"><span data-stu-id="511ca-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="511ca-120">A seguir, criamos um simulador de estado completo e executamos `GetEnergyByTrotterization` para obter a energia do estado do solo.</span><span class="sxs-lookup"><span data-stu-id="511ca-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="511ca-121">Observe que dois parâmetros são retornados.</span><span class="sxs-lookup"><span data-stu-id="511ca-121">Note that two parameters are returned.</span></span> <span data-ttu-id="511ca-122">`energyEst` é a estimativa da energia do estado do solo e deve ser `-1.137` em média.</span><span class="sxs-lookup"><span data-stu-id="511ca-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="511ca-123">`phaseEst` é a fase bruta retornada pelo algoritmo de estimativa de fase e é útil para diagnosticar quando ocorre um alias devido a um `trotterStep` muito grande.</span><span class="sxs-lookup"><span data-stu-id="511ca-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
