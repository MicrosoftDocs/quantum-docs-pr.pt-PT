---
title: Carregar um Hamiltoniano do ficheiro
description: Aprenda a gerar automaticamente um grande Hamiltonian usando o esquema broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907295"
---
# <a name="loading-a-hamiltonian-from-file"></a>Carregar um Hamiltoniano do ficheiro
Anteriormente, construímos hamiltonianos adicionando-lhe termos individuais. Embora isto seja bom para pequenos exemplos, a química quântica em escala requer hamiltonianos com milhões ou biliões de mandatos. Tais hamiltonianos, gerados por pacotes de química como o NWChem, são demasiado grandes para serem importados à mão. Nesta amostra, ilustramos como um `FermionHamiltonian` instância pode ser gerado automaticamente a partir de uma molécula representada pelo esquema de [Broombridge.](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) Para referência, pode-se inspecionar a amostra `LithiumHydrideGUI` fornecida ou a amostra `RunSimulation`. Está também disponível suporte limitado para importação do formato consumido pela [LIQUi>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Consideremos o exemplo da molécula de azoto, que é fornecida na pasta `IntegralData/YAML` do repositório de amostras. O método de carregamento do `Broombridge` esquema é simples.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

O esquema de Broombridge também contém sugestões para que o estado inicial seja preparado. As etiquetas, por exemplo, `"|G⟩"` ou `"|E1⟩"`, para estes estados podem ser vistas inspecionando o ficheiro. Para preparar estes estados iniciais, o `qSharpData` consumido pelos algoritmos quânticos Q# é obtido semelhante à [secção anterior,](xref:microsoft.quantum.chemistry.examples.energyestimate)mas com um parâmetro adicional selecionando o estado inicial desejado. Por exemplo,
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Todos os passos acima podem ser abreviados utilizando métodos de conveniência fornecidos da seguinte forma.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

Podemos também carregar um Hamiltonian a partir do formato LIQUigt; formato, utilizando uma sintaxe muito semelhante. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Seguindo este processo a partir de qualquer instância de Broombridge, ou qualquer passo intermédio, algoritmos quânticos como a estimativa da fase quântica podem ser executados no problema da estrutura electrónica especificado.
