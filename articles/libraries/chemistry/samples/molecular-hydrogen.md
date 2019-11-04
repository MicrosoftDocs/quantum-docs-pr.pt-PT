---
title: Obtendo estimativas de nível de energia | Microsoft Docs
description: Obtendo documentos de estimativas de nível de energia
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 0fd457b152083af364d924502c18bc0813e34b83
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442579"
---
# <a name="obtaining-energy-level-estimates"></a>Obter estimativas do nível de energia
Estimar os valores dos níveis de energia é um dos principais aplicativos da quantum química. Aqui, descrevemos como isso pode ser executado para o exemplo canônico de molecular Hydrogen. O exemplo referenciado nesta seção é `MolecularHydrogen` no repositório de exemplos de química. Um exemplo mais visual que plota a saída é a `MolecularHydrogenGUI` demonstração.

Nossa primeira etapa é construir o Hamiltonian que representa o molecular Hydrogen. Embora isso possa ser construído por meio da ferramenta NWChem, adicionamos manualmente os termos de Hamiltonian para brevidade neste exemplo.

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

A simulação do Hamiltonian exige a conversão dos operadores Fermion em operadores qubit. Essa conversão é executada por meio da codificação Jordânia-Wigner da seguinte maneira.

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

Agora, passamos o `qSharpData` representando o Hamiltonian para a função `TrotterStepOracle` na [simulação do Hamiltonian Dynamics](xref:microsoft.quantum.libraries.standard.algorithms). `TrotterStepOracle` retorna uma operação Quantum que aproxima a evolução em tempo real do Hamiltonian.

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

Agora podemos usar os algoritmos de estimativa de fase da biblioteca padrão para aprender a energia de estado terrestre usando a simulação acima. Isso requer a preparação de uma boa aproximação para o estado de aterramento do Quantum. As sugestões para essas aproximaçãos são fornecidas no esquema de `Broombridge`, mas essas sugestões estão ausentes, a abordagem padrão adiciona um número de `hamiltonian.NElectrons` elétrons ao greedily minimizar o termo diagonal um-. As funções e operações de estimativa de fase estão localizadas no [namespace Microsoft. Quantum. caracterization](xref:microsoft.quantum.characterization in DocFX notation).

O trecho a seguir mostra como a saída de evolução em tempo real da biblioteca de simulação de química pode ser integrada com a estimativa de fase Quantum.

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

Este código de Q # agora pode ser invocado a partir do programa de driver. A seguir, criamos um simulador de estado completo e executamos `GetEnergyByTrotterization` para obter a energia do estado do solo.

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

Observe que dois parâmetros são retornados. `energyEst` é a estimativa da energia do estado do solo e deve ser `-1.137` em média. `phaseEst` é a fase bruta retornada pelo algoritmo de estimativa de fase e é útil para diagnosticar quando ocorre um alias devido a um `trotterStep` muito grande.
