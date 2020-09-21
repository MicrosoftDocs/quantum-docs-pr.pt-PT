---
title: Assimetrias de Integrales Moleculares
description: Aprenda a usar o Q# tipo OrbitalIntegral para enumerar as assimetrias moleculares.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ebb8e9bda06967d3cfa002a7d074933d9135ada
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833818"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="e71e2-103">Assimetrias de Integrales Moleculares</span><span class="sxs-lookup"><span data-stu-id="e71e2-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="e71e2-104">A simetria inerente do Coulomb Hamiltonian, que é o Hamiltonian dado em [Modelos Quânticos para Sistemas Eletrónicos,](xref:microsoft.quantum.chemistry.concepts.quantummodels)que descreve eletrões que interagem electricamente entre si e com os núcleos, leva a uma série de simetrias que podem ser exploradas para comprimir os termos no Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="e71e2-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="e71e2-105">Em geral, se não forem feitas mais suposições sobre as funções de base $\psi_j$ então só temos que \start{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} que pode ser imediatamente visto a partir das integrais em [Modelos Quânticos de Sistemas Eletrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) ao notar que os seus valores permanecem idênticos se $p,q$ e $r,s$ forem trocados por anti-comutação.</span><span class="sxs-lookup"><span data-stu-id="e71e2-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="e71e2-106">Se assumirmos que os spin-orbitals são de valor real (como são para bases orbitais gaussianas) então temos ainda que \start{equação} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{{{{{{{{{{{{{{psrq}=h_{spqr}=h_{qrsp}.\tag{{★}\label{eq:hpqrsreal} \end{equation} Dado que tais pressupostos se mantêm, podemos usar as simetrias acima para reduzir os dados necessários para armazenar os elementos matricias do Hamiltonian por um fator de $8$; embora o faça, torna a importação de dados de uma forma consistentemente mais desafiante.</span><span class="sxs-lookup"><span data-stu-id="e71e2-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="e71e2-107">Felizmente, a biblioteca de simulação Hamiltonian tem sub-rotinas que podem ser usadas para importar ficheiros integrais de [LIQUI$\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) ou diretamente da [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="e71e2-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="e71e2-108">As integrais moleculares orbitais (ou seja, os $h \_ {pq}$ e $h \_ {pqrs}$ termos) como estes são representados usando o `OrbitalIntegral` tipo, que fornece uma série de funções úteis para expressar esta simetria.</span><span class="sxs-lookup"><span data-stu-id="e71e2-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
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

<span data-ttu-id="e71e2-109">Além de enumerar todas as integrais orbitais que são numericamente idênticas, uma lista de todos os índices spin-orbital contidos no Hamiltonian representado por um `OrbitalIntegral` pode ser gerado da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="e71e2-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="e71e2-110">Construção de Hamiltonianos Fermiónicos a partir de Integrales Moleculares</span><span class="sxs-lookup"><span data-stu-id="e71e2-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="e71e2-111">Em vez de construir um Hamiltonian Fermionic adicionando `FermionTerm` s, todos os termos correspondentes a cada parte orbital podem ser adicionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e71e2-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="e71e2-112">Por exemplo, o seguinte código enumera automaticamente todas as simetrias permutacionais e ordena os termos por ordem canónica:</span><span class="sxs-lookup"><span data-stu-id="e71e2-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
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
