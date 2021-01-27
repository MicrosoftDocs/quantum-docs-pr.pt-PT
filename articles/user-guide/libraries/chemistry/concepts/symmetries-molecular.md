---
title: Assimetrias de Integrales Moleculares
description: Aprenda a usar o Q# tipo OrbitalIntegral para enumerar as assimetrias moleculares.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2622285fd95eddf0d70402ae99dd18bfd8c38087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858830"
---
# <a name="symmetries-of-molecular-integrals"></a>Assimetrias de Integrales Moleculares

A simetria inerente do Coulomb Hamiltonian, que é o Hamiltonian dado em [Modelos Quânticos para Sistemas Eletrónicos,](xref:microsoft.quantum.chemistry.concepts.quantummodels)que descreve eletrões que interagem electricamente entre si e com os núcleos, leva a uma série de simetrias que podem ser exploradas para comprimir os termos no Hamiltonian.
Em geral, se não forem feitas mais suposições sobre as funções de base $\psi_j$ então só temos que \start{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} que pode ser imediatamente visto a partir das integrais em [Modelos Quânticos de Sistemas Eletrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) ao notar que os seus valores permanecem idênticos se $p,q$ e $r,s$ forem trocados por anti-comutação.

Se assumirmos que os spin-orbitals são de valor real (como são para bases orbitais gaussianas) então temos ainda que \start{equação} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{{★}\label{eq:hpqrsreal} \end{equation} Dado que tais pressupostos se mantêm, podemos usar as simetrias acima para reduzir os dados necessários para armazenar os elementos matricias do Hamiltonian por um fator de $8$; embora o faça, torna a importação de dados de uma forma consistentemente mais desafiante.
Felizmente, a biblioteca de simulação Hamiltonian tem sub-rotinas que podem ser usadas para importar ficheiros integrais de [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) ou diretamente da [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

As integrais moleculares orbitais (ou seja, os $h \_ {pq}$ e $h \_ {pqrs}$ termos) como estes são representados usando o `OrbitalIntegral` tipo, que fornece uma série de funções úteis para expressar esta simetria.
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

Além de enumerar todas as integrais orbitais que são numericamente idênticas, uma lista de todos os índices spin-orbital contidos no Hamiltonian representado por um `OrbitalIntegral` pode ser gerado da seguinte forma.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Construção de Hamiltonianos Fermiónicos a partir de Integrales Moleculares

Em vez de construir um Hamiltonian Fermionic adicionando `FermionTerm` s, todos os termos correspondentes a cada parte orbital podem ser adicionados automaticamente.
Por exemplo, o seguinte código enumera automaticamente todas as simetrias permutacionais e ordena os termos por ordem canónica: 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
