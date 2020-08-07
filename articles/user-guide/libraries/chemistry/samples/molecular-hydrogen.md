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
ms.openlocfilehash: a2df4b829a3f4946c6de6e6b80ad72a5bc192b2c
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869210"
---
# <a name="obtaining-energy-level-estimates"></a>Obter estimativas do nível de energia
Estimar os valores dos níveis de energia é uma das principais aplicações da química quântica. Este artigo descreve como pode fazer isto para o exemplo canónico do hidrogénio molecular. A amostra referenciada nesta secção está [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) no repositório de amostras de química. Um exemplo mais visual que traça a saída é a [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) demonstração.

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Estimando os valores energéticos do hidrogénio molecular

O primeiro passo é construir o Hamiltonian representando o hidrogénio molecular. Embora possa construir isto usando a ferramenta NWChem, para a brevidade, esta amostra adiciona os termos Hamiltonian manualmente.

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

Simular o Hamiltonian requer a conversão dos operadores de fermião para operadores qubit. Esta conversão é realizada através da codificação Jordan-Wigner da seguinte forma:

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

Em seguida, passe `qSharpData` , que representa o Hamiltonian, para a `TrotterStepOracle` função. `TrotterStepOracle`retorna uma operação quântica que aproxima a evolução em tempo real do Hamiltonian. Para obter mais informações, consulte [a dinâmica de Simulação de Hamiltonian.](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)

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

Neste ponto, você pode usar os [algoritmos](xref:microsoft.quantum.libraries.characterization) de estimativa de fase da biblioteca padrão para aprender a energia do estado do solo usando a simulação anterior. Isto requer a preparação de uma boa aproximação ao estado quântico. No esquema são fornecidas sugestões para tais [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) aproximações. No entanto, sem estas sugestões, a abordagem padrão adiciona uma série de `hamiltonian.NElectrons` eletrões para minimizar gananciosamente as energias diagonais de um eletrão. As funções e operações de estimativa de fase são fornecidas na notação DocFX no espaço de nomes [Microsoft.Quantum.Characterization.](xref:microsoft.quantum.characterization)

O seguinte corte mostra como a evolução em tempo real da biblioteca de simulação de química se integra com a estimativa da fase quântica.

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

Pode agora invocar o Q# código do programa anfitrião. O seguinte código C# cria um simulador de estado completo e corre `GetEnergyByTrotterization` para obter a energia do estado do solo.

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

A operação devolve dois parâmetros: 

- `energyEst`é a estimativa da energia do estado do solo e deve ser `-1.137` próximo, em média. 
- `phaseEst`é a fase bruta devolvida pelo algoritmo de estimativa de fase. Isto é útil para diagnosticar o pseudónimo quando ocorre devido a um `trotterStep` valor que é muito grande.
