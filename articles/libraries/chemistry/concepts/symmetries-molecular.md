---
title: Symmetries dos integrantes do molecular | Microsoft Docs
description: Documentos conceituais do Symmetries of molecular integrais
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442394"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries de integrantes do molecular

A simetria inerente do Coulomb Hamiltonian, que é o Hamiltonian fornecido em [modelos Quantum para sistemas eletrônicos](xref:microsoft.quantum.chemistry.concepts.quantummodels), que descreve elétrons interagindo eletricamente entre si e com a nuclei, leva a uma série de Symmetries que podem ser explorada para compactar os termos no Hamiltonian.
Em geral, se não forem feitas mais suposições sobre as funções de base $ \psi_j $, temos apenas que \begin{Equation} h_ {PQRS} = h_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation} que podem ser vistos imediatamente dos integrantes em [modelos Quantum para Sistemas eletrônicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) , ao observar que seus valores permanecem idênticos se $p, q $ e $r, s $ são trocados de anti-commutação.

Se presumirmos que os giros girados sejam de valor real (como são para bases orbital gaussianas), então, temos mais que \begin{Equation} h_ {PQRS} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{ Equation} considerando tais suposições, podemos usar o Symmetries acima para reduzir os dados necessários para armazenar os elementos de matriz do Hamiltonian por um fator de $8 $; Embora isso torne a importação de dados de forma consistente um pouco mais desafiador.
Felizmente, a biblioteca de simulação de Hamiltonian tem sub-rotinas que podem ser usadas para importar arquivos inteiros de [liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) ou diretamente do [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).

Molecular integrals orbital (ou seja, as $h\_{pq} $ e $h\_{PQRS} $ terms), como essas são representadas usando o tipo `OrbitalIntegral`, que fornece várias funções úteis para expressar essa simetria.
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

Além de enumerar todos os integrantes do orbital que são numericamente idênticos, uma lista de todos os índices de orbital de rotação contidas na Hamiltonian representada por um `OrbitalIntegral` pode ser gerada da seguinte maneira.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Construindo Fermionic Hamiltonians da molecular Integrals

Em vez de construir um Fermionic Hamiltonian adicionando `FermionTerm`s, todos os termos correspondentes a cada orbital integral podem ser adicionados automaticamente.
Por exemplo, o código a seguir enumera automaticamente todos os Symmetries permutais e ordena os termos em ordem canônica: 
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
