---
title: Simetrias de Integrais Moleculares
description: Aprenda a usar o tipo Q# OrbitalIntegral para enumerar simetrias moleculares.
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: b7e7b79af17af544c4a784eff08500498afc9f67
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904473"
---
# <a name="symmetries-of-molecular-integrals"></a>Simetrias de Integrais Moleculares

A simetria inerente do Coulomb Hamiltonian, que é o Hamiltoniano dado em [Modelos Quânticos para Sistemas Eletrónicos,](xref:microsoft.quantum.chemistry.concepts.quantummodels)que descreve eletrões interagindo electricamente uns com os outros e com os núcleos, leva a uma série de simetrias que podem ser exploradas para comprimir os termos no Hamiltoniano.
Em geral, se não forem feitos mais pressupostos sobre as funções base $\psi_j$ então só temos que \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} que pode ser imediatamente visto a partir dos integrais em [Modelos Quânticos de Sistemas Eletrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) ao notar que os seus valores permanecem idênticos se $p, q$ e $r, são trocados de com.

Se assumirmos que os orbitais de rotação são de valor real (como são para bases orbitais gaussianas) então temos ainda que \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_ {rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{ equação} Dado que tais pressupostos se mantêm, podemos usar as simetrias acima para reduzir os dados necessários para armazenar os elementos matriciais do Hamiltonian por um fator de $8$; embora fazê-lo torna a importação de dados de uma forma consistente um pouco mais desafiante.
Felizmente, a biblioteca de simulação hamiltoniana tem subrotinas que podem ser usadas para importar ficheiros integrais de [LIQUI$\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) ou diretamente da [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

As integrais orbitais moleculares (isto é, o $h\_{pq}$ e $h\_termos {pqrs}$) tais como estes são representados usando o tipo `OrbitalIntegral`, que fornece uma série de funções úteis para expressar esta simetria.
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

Além de enumerar todas as integrais orbitais que são numericamente idênticas, uma lista de todos os índices orbitais de rotação contidos no Hamiltonian representado por um `OrbitalIntegral` pode ser gerada da seguinte forma.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Construção de Hamiltonianos Fermiónicos a partir de Integrais Moleculares

Em vez de construir um Hamiltonian Fermiônico adicionando `FermionTerm`s, todos os termos correspondentes a cada integral orbital podem ser adicionados automaticamente.
Por exemplo, o seguinte código enumera automaticamente todas as simetrias permutais e ordena os termos por ordem canónica: 
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
